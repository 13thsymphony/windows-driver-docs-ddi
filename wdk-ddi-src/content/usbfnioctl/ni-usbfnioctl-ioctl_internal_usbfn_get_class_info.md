---
UID: NI.usbfnioctl.IOCTL_INTERNAL_USBFN_GET_CLASS_INFO
title: IOCTL_INTERNAL_USBFN_GET_CLASS_INFO
author: windows-driver-content
description: The class driver sends this request IO control code to retrieve information about the available pipes for a device, as configured in the registry.
old-location: buses\ioctl_internal_usbfn_get_class_info.htm
old-project: usbref
ms.assetid: 870D7D8C-B2FE-487A-9098-C004E6C7E159
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USBFN_USB_STRING, *PUSBFN_USB_STRING, USBFN_USB_STRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbfnioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_USBFN_GET_CLASS_INFO
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
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_GET_CLASS_INFO IOCTL



## -description
The class driver sends this request  IO control code to retrieve information about the available pipes for a device, as configured in the registry.



## -ioctlparameters

### -input-buffer
NULL.


### -input-buffer-length
None.


### -output-buffer
A pointer to a buffer that contains a <a href="buses.usbfn_class_information_packet">USBFN_CLASS_INFORMATION_PACKET</a> structure. Upon completion, UFX populates the structure with the name, the device interface GUID, and details of the interface when operating at a particular bus speed.


### -output-buffer-length
The size of a <a href="buses.usbfn_class_information_packet">USBFN_CLASS_INFORMATION_PACKET</a> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks
The class driver should send this IOCTL request during initialization so that it can enumerate the endpoints and attributes.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbfnioctl.h</dt>
</dl>
</td>
</tr>
</table>