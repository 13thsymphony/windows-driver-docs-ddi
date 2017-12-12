---
UID: NI.usbfnioctl.IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
title: IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
author: windows-driver-content
description: The class driver sends this request to send a zero-length control status handshake on endpoint 0 in the IN direction.
old-location: buses\_ioctl_internal_usbfn_control_status_handshake_in.htm
old-project: usbref
ms.assetid: 5839C1A8-6638-4A42-B7C1-168071C99800
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
req.alt-api: IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN
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

# IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN IOCTL



## -description
The class driver sends this request to send a zero-length control status handshake on endpoint 0 in the IN direction. 



## -ioctlparameters

### -input-buffer
A <b>USBFNPIPEID</b> type value that indicates the pipe ID. The pipe ID of the default control endpoint is 0.


### -input-buffer-length
The size of a <b>USBFNPIPEID</b> type.


### -output-buffer
NULL.


### -output-buffer-length
NULL.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. 


## -remarks
This request must be sent after sending the <a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.

UFX forwards this IOCTL request to the transfer queue created for the endpoint by <a href="buses.ufxendpointcreate">UfxEndpointCreate</a>.


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