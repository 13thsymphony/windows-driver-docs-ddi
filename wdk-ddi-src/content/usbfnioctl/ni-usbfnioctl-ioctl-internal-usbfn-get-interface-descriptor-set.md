---
UID: NI.usbfnioctl.IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET
title: IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET
author: windows-driver-content
description: The class driver sends this request to get the entire USB interface descriptor set for a function on the device.
old-location: buses\ioctl_internal_usbfn_get_interface_descriptor_set_.htm
old-project: usbref
ms.assetid: AF5E2559-151B-4176-A25E-6A1955747F1A
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: USBFN_USB_STRING, USBFN_USB_STRING, *PUSBFN_USB_STRING
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
req.alt-api: IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET
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
req.iface: 
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET IOCTL



## -description
<p>The class driver sends this request to get the entire USB interface descriptor set for a function on the device.</p>


## -ioctlparameters

### -input-buffer
<p>A pointer to a buffer that contains a <a href="..\usbfnbase\ns-usbfnbase--usbfn-interface-info.md">USBFN_INTERFACE_INFO</a> structure. </p>

### -input-buffer-length
<p>The length of the input buffer must be at least <code>sizeof(USBFN_INTERFACE_INFO)</code>.</p>

<p>The length of the input buffer must be at least <code>sizeof(USBFN_INTERFACE_INFO)</code>.</p>

### -output-buffer
<p>A pointer to a buffer that contains a <a href="..\usbfnbase\ns-usbfnbase--usbfn-interface-info.md">USBFN_INTERFACE_INFO</a> structure. USB function class extension (UFX) populates the structure with the entire interface descriptor set including its endpoint descriptors.</p>

<p>A pointer to a buffer that contains a <a href="..\usbfnbase\ns-usbfnbase--usbfn-interface-info.md">USBFN_INTERFACE_INFO</a> structure. USB function class extension (UFX) populates the structure with the entire interface descriptor set including its endpoint descriptors.</p>

<p>A pointer to a buffer that contains a <a href="..\usbfnbase\ns-usbfnbase--usbfn-interface-info.md">USBFN_INTERFACE_INFO</a> structure. USB function class extension (UFX) populates the structure with the entire interface descriptor set including its endpoint descriptors.</p>

### -output-buffer-length
<p>The length of the output buffer must be at least <code>sizeof(USBFN_INTERFACE_INFO)</code>. </p>

<p>The length of the output buffer must be at least <code>sizeof(USBFN_INTERFACE_INFO)</code>. </p>

<p>The length of the output buffer must be at least <code>sizeof(USBFN_INTERFACE_INFO)</code>. </p>

<p>The length of the output buffer must be at least <code>sizeof(USBFN_INTERFACE_INFO)</code>. </p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. </p>

<p>If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. </p>

<p>If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. </p>

<p>If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. </p>

<p>If the request is successful, the USB function class extension (UFX) returns STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it returns a status value for which NT_SUCCESS(status) equals FALSE. </p>

## -remarks
<p>This request must be sent after sending the <a href="..\usbfnioctl\ni-usbfnioctl-ioctl-internal-usbfn-activate-usb-bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a> request.</p>

<p>The length of the entire interface descriptor is variable. The class driver might need to send this IOCTL request twice to get the entire descriptor set.</p>

<p>If the length of the entire descriptor set is greater than the  specified output buffer length, UFX sets the <b>Size</b> member of <a href="..\usbfnbase\ns-usbfnbase--usbfn-interface-info.md">USBFN_INTERFACE_INFO</a> to the actual buffer length and fails the request with STATUS_BUFFER_TOO_SMALL. The driver must then allocated an output buffer of length specified by <b>Size</b> and resend the request. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usbfnioctl.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usbfnbase\ns-usbfnbase--usbfn-interface-info.md">USBFN_INTERFACE_INFO</a>
</dt>
<dt>
<a href="..\usbfnioctl\ni-usbfnioctl-ioctl-internal-usbfn-activate-usb-bus.md">IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET control code%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
