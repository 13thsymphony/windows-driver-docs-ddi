---
UID: NF.sercx.SerCx2SaveReceiveFifoOnD0Exit
title: SerCx2SaveReceiveFifoOnD0Exit function
author: windows-driver-content
description: The SerCx2SaveReceiveFifoOnD0Exit method informs version 2 of the serial framework extension (SerCx2) that the receive FIFO of the serial controller hardware contains data that should be saved before the serial controller enters a device low-power state.
old-location: serports\sercx2savereceivefifoond0exit.htm
old-project: serports
ms.assetid: 689306DE-F83A-4C5D-B79A-DEBF2D5E79B3
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SerCx2SaveReceiveFifoOnD0Exit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SerCx2SaveReceiveFifoOnD0Exit
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
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# SerCx2SaveReceiveFifoOnD0Exit function



## -description
The <b>SerCx2SaveReceiveFifoOnD0Exit</b> method informs version 2 of the serial framework extension (SerCx2) that the receive FIFO of the serial controller hardware contains data that should be saved before the serial controller enters a device low-power state.



## -syntax

````
VOID SerCx2SaveReceiveFifoOnD0Exit(
  [in] SERCX2PIORECEIVE PioReceive,
  [in] ULONG            FifoSize
);
````


## -parameters

### -param PioReceive [in]

A <a href="serports.sercx2pioreceive_object_handle">SERCX2PIORECEIVE</a> handle to a PIO-receive object. The serial controller driver previously called the <a href="serports.sercx2pioreceivecreate">SerCx2PioReceiveCreate</a> method to create this object.


### -param FifoSize [in]

The number of bytes of unread data that the transmit FIFO contains.


## -returns
None.


## -remarks
When the serial controller is about to enter a low-power state, SerCx2 and the serial controller driver must save any bytes of unread data that might remain in the receive FIFO. Otherwise, this data will be lost when the serial controller enters the low-power state. To request assistance from SerCx2 to save this data, the driver calls <b>SerCx2SaveReceiveFifoOnD0Exit</b>.

The driver framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a> or <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled.md">EvtDeviceD0ExitPreInterruptsDisabled</a> event callback function to tell the driver to prepare the serial controller to exit the D0 device state. In response, this function first deasserts the <i>ready to send</i> (RTS) line to tell the device on the other end of the serial connection to not send any more data. Next, the function calls <b>SerCx2SaveReceiveFifoOnD0Exit</b>.

<b>SerCx2SaveReceiveFifoOnD0Exit</b> calls the driver's <a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_read_buffer.md">EvtSerCx2PioReceiveReadBuffer</a> event callback function to retrieve the data from the receive FIFO. In this call, SerCx2 supplies, as a parameter, a pointer to an internal software buffer that SerCx2 maintains for the purpose of saving unread data from the receive FIFO in preparation to enter a low-power state.

Later, after a client sends a read (<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>) request to the serial controller, SerCx2 copies the bytes from this internal software buffer to the read buffer in the request.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.1.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>2.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled.md">EvtDeviceD0ExitPreInterruptsDisabled</a>
</dt>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_pio_receive_read_buffer.md">EvtSerCx2PioReceiveReadBuffer</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>
</dt>
<dt>
<a href="serports.sercx2pioreceive_object_handle">SERCX2PIORECEIVE</a>
</dt>
<dt>
<a href="serports.sercx2pioreceivecreate">SerCx2PioReceiveCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2SaveReceiveFifoOnD0Exit method%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

