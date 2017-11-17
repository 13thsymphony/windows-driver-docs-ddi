---
UID: NC.sercx.EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER
title: EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER
author: windows-driver-content
description: The EvtSerCx2PioTransmitWriteBuffer event callback function is called by version 2 of the serial framework extension (SerCx2) to use programmed I/O (PIO) to transfer the contents of a write buffer to the transmit FIFO in the serial controller.
old-location: serports\evtsercx2piotransmitwritebuffer.htm
ms.assetid: 28DD175B-9869-4CFC-9BDD-172DA7E015DE
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: serports
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: EvtSerCx2PioTransmitWriteBuffer
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
ms.keywords: SENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.iface: 
req.product: Windows 10 or later.
---

# EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER callback



## -description
<p>The <i>EvtSerCx2PioTransmitWriteBuffer</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to use programmed I/O (PIO) to transfer the contents of a write buffer to the transmit FIFO in the serial controller.</p>


## -prototype

````
EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER EvtSerCx2PioTransmitWriteBuffer;

ULONG EvtSerCx2PioTransmitWriteBuffer(
  _In_ SERCX2PIOTRANSMIT PioTransmit,
  _In_ PUCHAR            Buffer,
  _In_ ULONG             Length
)
{ ... }
````


## -parameters
<dl>

### -param <i>PioTransmit</i> [in]

<dd>
<p>A <a href="serports.sercx2piotransmit_object_handle">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> method to create this object.</p>
</dd>

### -param <i>Buffer</i> [in]

<dd>
<p>A pointer to the write buffer. This parameter is the virtual address of a locked-down buffer in system memory.</p>
</dd>

### -param <i>Length</i> [in]

<dd>
<p>The number of bytes in the write buffer that are available to be transmitted.</p>
</dd>
</dl>

## -returns
<p>The <i>EvtSerCx2PioTransmitWriteBuffer</i> function returns the number of bytes of data it successfully transferred from the write buffer to the transmit FIFO in the serial controller hardware.</p>

## -remarks
<p>Your serial controller driver must implement this function. The driver registers the function in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.</p>

<p>SerCx2 might call the <i>EvtSerCx2PioTransmitWriteBuffer</i> function more than once during a PIO-transmit transaction. A single <i>EvtSerCx2PioTransmitWriteBuffer</i> call is sufficient if this call can transfer the full contents of the write buffer to the transmit FIFO. Otherwise, SerCx2 continues to call this function, as more space becomes available in the transmit FIFO, until the write buffer is emptied.</p>

<p>Starting with the first byte in the write buffer, the <i>EvtSerCx2PioTransmitWriteBuffer</i> function uses PIO to transfer as many bytes as it can from the buffer to the transmit FIFO. The function continues to transfer data from the buffer for as long as the buffer is not empty and the <i>line status register</i> (LSR) indicates that the FIFO can accept more data. If the LSR indicates that the FIFO can accept no more data, the function returns without emptying the buffer. Otherwise, the function transfers all the bytes in the buffer and returns. In either case, the value returned by this function is the number of bytes of data that were successfully transferred from the write buffer to the transmit FIFO.</p>

<p>Typically, the <i>EvtSerCx2PioTransmitWriteBuffer</i> function does not enable any interrupts. Instead, if the function is unable to transfer the entire contents of the write buffer to the transmit FIFO, SerCx2 calls the <a href="https://msdn.microsoft.com/05E5F48B-4E82-4BC3-B6D1-7E9E3435BDB3">EvtSerCx2PioTransmitEnableReadyNotification</a> event callback function to enable a ready notification, and this function enables an interrupt that occurs when the transmit FIFO becomes empty.</p>

<p>For each successive call to the <i>EvtSerCx2PioTransmitWriteBuffer</i> function, SerCx2 adjusts <i>Buffer</i> to point to the remaining data in the buffer, and sets <i>Length</i> to the number of data bytes that remain in the buffer.</p>

<p>The ready notification is never enabled when SerCx2 calls the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function. However, SerCx2 might call this function from the same thread from which the driver called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265273">SerCx2PioTransmitReady</a> method.</p>

<p>If the driver implements an <a href="https://msdn.microsoft.com/2E3652CB-24F1-4467-AF1D-CFD52392B2DB">EvtSerCx2PioTransmitInitializeTransaction</a> function, SerCx2 calls this function at the start of a PIO-transmit transaction, before the first call to the <i>EvtSerCx2PioTransmitWriteBuffer</i> function. If the driver implements an <a href="https://msdn.microsoft.com/48300C50-47B7-47DC-BDE5-3847E1EAE820">EvtSerCx2PioTransmitCleanupTransaction</a> function, SerCx2 calls this function at the end of a PIO-transmit transaction, after the last <i>EvtSerCx2PioTransmitWriteBuffer</i> call, and after any calls to the <a href="https://msdn.microsoft.com/A21E14DA-0B76-4DA2-B628-C3A4DE843FA9">EvtSerCx2PioTransmitDrainFifo</a>, <a href="https://msdn.microsoft.com/DAAE9C91-F83F-4D14-8851-7B5DEEA340B3">EvtSerCx2PioTransmitCancelDrainFifo</a>, and <a href="https://msdn.microsoft.com/2BB02F84-01C1-432D-A4A9-6035F3ED32D7">EvtSerCx2PioTransmitPurgeFifo</a> functions, if they are implemented.</p>

<p>For more information about PIO-transmit transactions, see <a href="NULL">SerCx2 PIO-Transmit Transactions</a>.</p>

<p>To define an <i>EvtSerCx2PioTransmitWriteBuffer</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtSerCx2PioTransmitWriteBuffer</i> callback function that is named <code>MyPioTransmitWriteBuffer</code>, use the <b>EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER</b> function type, as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.</p>

<p>Your serial controller driver must implement this function. The driver registers the function in the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> call that creates the PIO-transmit object.</p>

<p>SerCx2 might call the <i>EvtSerCx2PioTransmitWriteBuffer</i> function more than once during a PIO-transmit transaction. A single <i>EvtSerCx2PioTransmitWriteBuffer</i> call is sufficient if this call can transfer the full contents of the write buffer to the transmit FIFO. Otherwise, SerCx2 continues to call this function, as more space becomes available in the transmit FIFO, until the write buffer is emptied.</p>

<p>Starting with the first byte in the write buffer, the <i>EvtSerCx2PioTransmitWriteBuffer</i> function uses PIO to transfer as many bytes as it can from the buffer to the transmit FIFO. The function continues to transfer data from the buffer for as long as the buffer is not empty and the <i>line status register</i> (LSR) indicates that the FIFO can accept more data. If the LSR indicates that the FIFO can accept no more data, the function returns without emptying the buffer. Otherwise, the function transfers all the bytes in the buffer and returns. In either case, the value returned by this function is the number of bytes of data that were successfully transferred from the write buffer to the transmit FIFO.</p>

<p>Typically, the <i>EvtSerCx2PioTransmitWriteBuffer</i> function does not enable any interrupts. Instead, if the function is unable to transfer the entire contents of the write buffer to the transmit FIFO, SerCx2 calls the <a href="https://msdn.microsoft.com/05E5F48B-4E82-4BC3-B6D1-7E9E3435BDB3">EvtSerCx2PioTransmitEnableReadyNotification</a> event callback function to enable a ready notification, and this function enables an interrupt that occurs when the transmit FIFO becomes empty.</p>

<p>For each successive call to the <i>EvtSerCx2PioTransmitWriteBuffer</i> function, SerCx2 adjusts <i>Buffer</i> to point to the remaining data in the buffer, and sets <i>Length</i> to the number of data bytes that remain in the buffer.</p>

<p>The ready notification is never enabled when SerCx2 calls the <i>EvtSerCx2PioTransmitEnableReadyNotification</i> function. However, SerCx2 might call this function from the same thread from which the driver called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265273">SerCx2PioTransmitReady</a> method.</p>

<p>If the driver implements an <a href="https://msdn.microsoft.com/2E3652CB-24F1-4467-AF1D-CFD52392B2DB">EvtSerCx2PioTransmitInitializeTransaction</a> function, SerCx2 calls this function at the start of a PIO-transmit transaction, before the first call to the <i>EvtSerCx2PioTransmitWriteBuffer</i> function. If the driver implements an <a href="https://msdn.microsoft.com/48300C50-47B7-47DC-BDE5-3847E1EAE820">EvtSerCx2PioTransmitCleanupTransaction</a> function, SerCx2 calls this function at the end of a PIO-transmit transaction, after the last <i>EvtSerCx2PioTransmitWriteBuffer</i> call, and after any calls to the <a href="https://msdn.microsoft.com/A21E14DA-0B76-4DA2-B628-C3A4DE843FA9">EvtSerCx2PioTransmitDrainFifo</a>, <a href="https://msdn.microsoft.com/DAAE9C91-F83F-4D14-8851-7B5DEEA340B3">EvtSerCx2PioTransmitCancelDrainFifo</a>, and <a href="https://msdn.microsoft.com/2BB02F84-01C1-432D-A4A9-6035F3ED32D7">EvtSerCx2PioTransmitPurgeFifo</a> functions, if they are implemented.</p>

<p>For more information about PIO-transmit transactions, see <a href="NULL">SerCx2 PIO-Transmit Transactions</a>.</p>

<p>To define an <i>EvtSerCx2PioTransmitWriteBuffer</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtSerCx2PioTransmitWriteBuffer</i> callback function that is named <code>MyPioTransmitWriteBuffer</code>, use the <b>EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER</b> function type, as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER</b> function type is defined in the Sercx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.</p>

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
<a href="https://msdn.microsoft.com/DAAE9C91-F83F-4D14-8851-7B5DEEA340B3">EvtSerCx2PioTransmitCancelDrainFifo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/A21E14DA-0B76-4DA2-B628-C3A4DE843FA9">EvtSerCx2PioTransmitDrainFifo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/05E5F48B-4E82-4BC3-B6D1-7E9E3435BDB3">EvtSerCx2PioTransmitEnableReadyNotification</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/2E3652CB-24F1-4467-AF1D-CFD52392B2DB">EvtSerCx2PioTransmitInitializeTransaction</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/2BB02F84-01C1-432D-A4A9-6035F3ED32D7">EvtSerCx2PioTransmitPurgeFifo</a>
</dt>
<dt>
<a href="serports.sercx2piotransmit_object_handle">SERCX2PIOTRANSMIT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PIO_TRANSMIT_WRITE_BUFFER callback function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
