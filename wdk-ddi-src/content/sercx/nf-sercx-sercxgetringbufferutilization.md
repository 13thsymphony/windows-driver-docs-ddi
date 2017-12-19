---
UID: NF.sercx.SerCxGetRingBufferUtilization
title: SerCxGetRingBufferUtilization function
author: windows-driver-content
description: The SerCxGetRingBufferUtilization method enables the serial controller driver to determine how much of the type-ahead ring buffer is currently filled by data received from the serial port.
old-location: serports\sercxgetringbufferutilization.htm
old-project: serports
ms.assetid: 8D4B8682-5713-47D6-A18E-F2EE44614DFB
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCxGetRingBufferUtilization
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SerCxGetRingBufferUtilization
req.alt-loc: 1.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# SerCxGetRingBufferUtilization function



## -description
The <b>SerCxGetRingBufferUtilization</b> method enables the serial controller driver to determine how much of the type-ahead ring buffer is currently filled by data received from the serial port.



## -syntax

````
VOID SerCxGetRingBufferUtilization(
  [in]            WDFDEVICE Device,
  [out, optional] PULONG    BytesUsed,
  [out, optional] PULONG    BufferSize
);
````


## -parameters

### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


### -param BytesUsed [out, optional]

The number of bytes of unread data that are currently contained in the type-ahead ring buffer that is used to store received data.


### -param BufferSize [out, optional]

The size, in bytes, of the type-ahead ring buffer that is used to store received data.


## -returns
None.


## -remarks
The serial controller driver calls this function to determine how much storage space is available in the type-ahead ring buffer. The serial controller extension (SerCx) maintains this buffer to contain data that the serial controller driver receives from the serial port when no read request from the client is currently being processed. This function provides the information that the driver requires to accurately perform software flow control (XON/XOFF).

To implement software flow control, the serial controller driver monitors the amount of space available in the type-ahead ring buffer. The available space, in bytes, is equal to <i>BufferSize</i> - <i>BytesUsed</i>. When the available space falls below a client-specified threshold, <b>XoffLimit</b>, the serial controller driver transmits an XOFF character to tell the transmitting port to pause transmission. Later, when the available space rises above a client-specified threshold, <b>XonLimit</b>, the driver transmits an XON character to tell the transmitting port to resume transmission. Typically, the client specified these two thresholds in a previous <a href="..\ntddser\ni-ntddser-ioctl_serial_set_handflow.md">IOCTL_SERIAL_SET_HANDFLOW</a> I/O control request.

SerCx evaluates the available space in the type-ahead ring buffer in the context of the current flow control and handshaking settings. After the type-ahead ring buffer empties completely, SerCx calls the driver's <a href="..\sercx\nc-sercx-evt_sercx_receive.md">EvtSerCxReceive</a> callback function so that the driver can send an XON and resume receiving data. The <i>EvtSerCxReceive</i> function can call <b>SerCxGetRingBufferUtilization</b> to determine whether to send an XON.


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
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>1.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx_receive.md">EvtSerCxReceive</a>
</dt>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_set_handflow.md">IOCTL_SERIAL_SET_HANDFLOW</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxGetRingBufferUtilization method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

