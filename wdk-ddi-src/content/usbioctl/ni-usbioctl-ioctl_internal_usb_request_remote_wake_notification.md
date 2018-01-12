---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION
title: IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION I/O request is sent by the driver of a Universal Serial Bus (USB) multi-function device (composite driver) to request remote wake-up notifications from a specific function in the device.
old-location: buses\ioctl_internal_usb_usbdevice_remote_wake_notification.htm
old-project: usbref
ms.assetid: 1EAFEFAD-A8FC-4A79-9332-75B143EEEB18
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_HUB_TYPE, USB_HUB_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION
req.alt-loc: Usbioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION IOCTL



## -description
The <b>IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION</b> 
   I/O request is sent by the driver of a Universal Serial Bus (USB) multi-function device (composite driver) to request remote wake-up notifications from a specific function in the device.

<b>IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION</b> is a kernel-mode I/O control request. This request targets the USB hub physical device object (PDO). 



## -ioctlparameters

### -input-buffer
<b>Parameters.Others.Argument1</b> points to a caller-allocated and initialized <a href="..\usbdlib\ns-usbdlib-_request_remote_wake_notification.md">REQUEST_REMOTE_WAKE_NOTIFICATION</a> structure that contains information about the function whose resume signal the driver is interested in. That information includes  the function handle and the interface with which the function is associated.


### -input-buffer-length
The size of a <a href="..\usbdlib\ns-usbdlib-_request_remote_wake_notification.md">REQUEST_REMOTE_WAKE_NOTIFICATION</a> structure.


### -output-buffer
None. 


### -output-buffer-length
None. 


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The hub or port driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbioctl.h (include Usbioctl.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/91F96D30-CD18-4DDC-BA5A-7BFFA8FBED9B">How to Implement Function Suspend in a Composite Driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

