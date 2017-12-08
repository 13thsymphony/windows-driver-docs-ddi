---
UID: NF.sercx.SerCxProgressTransmit
title: SerCxProgressTransmit function
author: windows-driver-content
description: The SerCxProgressTransmit method reports the progress of the current write (transmit) operation.
old-location: serports\sercxprogresstransmit.htm
old-project: serports
ms.assetid: 4B5301B6-8C10-4C8E-A9D2-28D2484A907A
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SerCxProgressTransmit
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
req.alt-api: SerCxProgressTransmit
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

# SerCxProgressTransmit function



## -description
The <b>SerCxProgressTransmit</b> method reports the progress of the current write (transmit) operation.


## -syntax

````
NTSTATUS SerCxProgressTransmit(
  [in] WDFDEVICE    Device,
  [in] ULONG        BytesTransmitted,
  [in] SERCX_STATUS TransmitStatus
);
````


## -parameters

### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.

### -param BytesTransmitted [in]

The number of bytes of data that the caller copied from the transmit buffer that was obtained by the latest call to the <a href="serports.sercxretrievetransmitbuffer">SerCxRetrieveTransmitBuffer</a> method.

### -param TransmitStatus [in]

The current status of the transmit operation. Set this parameter to one of the following values:
<ul>
<li><b>SerCxStatusSuccess</b></li>
<li><b>SerCxStatusCancelled</b></li>
</ul>
For more information about these values, see <a href="serports.sercx_status">SERCX_STATUS</a>.
<div class="alert"><b>Note</b>  The <b>SerCxStatusTimeout</b> value is valid only for receive operations. No interval time-out can be specified for a transmit operation. For more information, see <a href="serports.serial_timeouts">SERIAL_TIMEOUTS</a>.</div>
<div> </div>

## -returns
<b>SerCxProgressTransmit</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>BytesTransmitted</i> value exceeds the available buffer length; or the <i>TransmitStatus</i> value is not valid.
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The method was called at the wrong IRQL; or the WDFDEVICE handle is not valid; or the driver has not obtained an output buffer for this transmit operation.
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>The transmit operation has already been canceled.

 

## -remarks
The serial controller driver calls this method to report progress on an outstanding write operation. Typically, the serial controller driver calls this method from its DMA completion callback (if the driver uses DMA to read the data) or from its transmit/receive DPC function (if PIO is used).

If the <b>SerCxProgressTransmit</b> call does not complete all outstanding work for the write operation, the caller must call <a href="serports.sercxretrievetransmitbuffer">SerCxRetrieveTransmitBuffer</a> again to get a new buffer descriptor and continue to transmit data.

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
<a href="serports.sercx_status">SERCX_STATUS</a>
</dt>
<dt>
<a href="serports.serial_timeouts">SERIAL_TIMEOUTS</a>
</dt>
<dt>
<a href="serports.sercxretrievetransmitbuffer">SerCxRetrieveTransmitBuffer</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCxProgressTransmit method%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
