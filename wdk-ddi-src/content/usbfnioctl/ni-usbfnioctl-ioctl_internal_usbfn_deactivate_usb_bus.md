---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_DEACTIVATE_USB_BUS
title: IOCTL_INTERNAL_USBFN_DEACTIVATE_USB_BUS
author: windows-driver-content
description: Do not use.
old-location: buses\ioctl_internal_usbfn_deactivate_usb_bus.htm
old-project: usbref
ms.assetid: 73BD1E87-150F-4C91-811E-D7139E98B365
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USBFN_USB_STRING, *PUSBFN_USB_STRING, USBFN_USB_STRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbfnioctl.h
req.include-header: Usbfnioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_USBFN_DEACTIVATE_USB_BUS
req.alt-loc: usbfnioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: *PUSBFN_USB_STRING, USBFN_USB_STRING
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_DEACTIVATE_USB_BUS IOCTL



## -description
Do not use.



## -ioctlparameters

### -input-buffer
NULL.


### -input-buffer-length
None.


### -output-buffer
NULL.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbfnioctl.h (include Usbfnioctl.h)</dt>
</dl>
</td>
</tr>
</table>