---
UID: NC.sercx.EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO
title: EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO
author: windows-driver-content
description: The EvtSerCx2PioTransmitCancelDrainFifo event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a previous request to drain the transmit FIFO in the serial controller hardware.
old-location: serports\evtsercx2piotransmitcanceldrainfifo.htm
old-project: serports
ms.assetid: DAAE9C91-F83F-4D14-8851-7B5DEEA340B3
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtSerCx2PioTransmitCancelDrainFifo
req.alt-loc: 2.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IRQL <= DISPATCH_LEVEL.
req.iface: 
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO callback



## -description
<p>The <i>EvtSerCx2PioTransmitCancelDrainFifo</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a previous request to drain the transmit FIFO in the serial controller hardware.</p>


## -prototype

````
EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO EvtSerCx2PioTransmitCancelDrainFifo;

BOOLEAN EvtSerCx2PioTransmitCancelDrainFifo(
  _In_ SERCX2PIOTRANSMIT PioTransmit
)
{ ... }
````


## -parameters
<dl>

### -param PioTransmit [in]

<dd>
<p>A <a href="serports.sercx2piotransmit_object_handle">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method to create this object.</p>
</dd>
</dl>

## -returns
<p>The <i>EvtSerCx2PioTransmitCancelDrainFifo</i> function returns <b>TRUE</b> if it successfully cancels the pending drain request, and the serial controller driver can guarantee that it will not call the <a href="..\sercx\nf-sercx-sercx2piotransmitdrainfifocomplete.md">SerCx2PioTransmitDrainFifoComplete</a> method to notify SerCx2 that the FIFO is drained. Otherwise, this function returns <b>FALSE</b> to indicate that the driver has already called or is about to call <b>SerCx2PioTransmitDrainFifoComplete</b>.</p>

## -remarks
<p>Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.</p>

<p>Your driver should implement an <i>EvtSerCx2PioTransmitCancelDrainFifo</i> function if the serial controller has a hardware FIFO (or similar buffering mechanism) to hold transmit data. If your driver implements this function, it must also implement the <a href="..\sercx\nc-sercx-evt-sercx2-pio-transmit-drain-fifo.md">EvtSerCx2PioTransmitDrainFifo</a> and <a href="..\sercx\nc-sercx-evt-sercx2-pio-transmit-purge-fifo.md">EvtSerCx2PioTransmitPurgeFifo</a> event callback functions.</p>

<p>SerCx2 calls the <i>EvtSerCx2PioTransmitDrainFifo</i> event callback function to ask the serial controller driver to drain the transmit FIFO, and then waits for the serial controller driver to call <a href="..\sercx\nf-sercx-sercx2piotransmitdrainfifocomplete.md">SerCx2PioTransmitDrainFifoComplete</a>. A drain operation can take an indefinite amount of time to finish. Thus, if the write request times out or is canceled while the drain operation is in progress, SerCx2 calls the <i>EvtSerCx2PioTransmitCancelDrainFifo</i> function to cancel the pending drain operation before it finishes.</p>

<p>For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.</p>

<p>To define an <i>EvtSerCx2PioTransmitCancelDrainFifo</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtSerCx2PioTransmitCancelDrainFifo</i> callback function that is named <code>MyPioTransmitCancelDrainFifo</code>, use the <b>EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO</b> function type, as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.1.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>2.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Called at IRQL &lt;= DISPATCH_LEVEL.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\sercx\nc-sercx-evt-sercx2-pio-transmit-drain-fifo.md">EvtSerCx2PioTransmitDrainFifo</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt-sercx2-pio-transmit-purge-fifo.md">EvtSerCx2PioTransmitPurgeFifo</a>
</dt>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl-serial-purge.md">IOCTL_SERIAL_PURGE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>
</dt>
<dt>
<a href="serports.sercx2piotransmit_object_handle">SERCX2PIOTRANSMIT</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2piotransmitdrainfifocomplete.md">SerCx2PioTransmitDrainFifoComplete</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_TRANSMIT_CANCEL_DRAIN_FIFO callback function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
