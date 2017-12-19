---
UID: NE.sercx._SERCX_STATUS
title: _SERCX_STATUS
author: windows-driver-content
description: The SERCX_STATUS enumeration indicates the status of a serial receive or transmit operation.
old-location: serports\sercx_status.htm
old-project: serports
ms.assetid: 7EF129C7-25C3-49D2-8FC5-FFA1C4E77935
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SERCX_STATUS, *PSERCX_STATUS, SERCX_STATUS, PSERCX_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sercx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SERCX_STATUS
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _SERCX_STATUS enumeration



## -description
The <b>SERCX_STATUS</b> enumeration indicates the status of a serial receive or transmit operation.



## -syntax

````
typedef enum _SERCX_STATUS { 
  SerCxStatusSuccess    = STATUS_SUCCESS,
  SerCxStatusCancelled  = STATUS_CANCELLED,
  SerCxStatusTimeout    = STATUS_TIMEOUT
} SERCX_STATUS;
````


## -enum-fields

### -field SerCxStatusSuccess

The operation is proceeding successfully.


### -field SerCxStatusCancelled

The operation was canceled.


### -field SerCxStatusTimeout

The operation timed out. This enumeration value applies only to read interval time-outs for receive operations. For more information, see the description of the <b>ReadIntervalTimeout</b> member in <a href="serports.serial_timeouts">SERIAL_TIMEOUTS</a>.


## -remarks
The <a href="serports.sercxprogressreceive">SerCxProgressReceive</a> and <a href="serports.sercxprogresstransmit">SerCxProgressTransmit</a> methods have parameters that are <b>SERCX_STATUS</b> enumeration values.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 8.

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
</table>

## -see-also
<dl>
<dt>
<a href="serports.sercxprogressreceive">SerCxProgressReceive</a>
</dt>
<dt>
<a href="serports.sercxprogresstransmit">SerCxProgressTransmit</a>
</dt>
<dt>
<a href="serports.serial_timeouts">SERIAL_TIMEOUTS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX_STATUS enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

