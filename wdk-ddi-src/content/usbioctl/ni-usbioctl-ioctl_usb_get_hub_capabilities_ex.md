---
UID: NI:usbioctl.IOCTL_USB_GET_HUB_CAPABILITIES_EX
title: IOCTL_USB_GET_HUB_CAPABILITIES_EX
author: windows-driver-content
description: The IOCTL_USB_GET_HUB_CAPABILITIES_EX I/O control request retrieves the capabilities of a USB hub.IOCTL_USB_GET_HUB_CAPABILITIES_EX is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).
old-location: buses\ioctl_usb_get_hub_capabilities_ex.htm
old-project: usbref
ms.assetid: 49c25f30-8eff-4894-8a82-a90c5a7d9aa4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_HUB_TYPE, USB_HUB_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_USB_GET_HUB_CAPABILITIES_EX
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
req.irql: 
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_HUB_CAPABILITIES_EX IOCTL



## -description

The <b>IOCTL_USB_GET_HUB_CAPABILITIES_EX</b> I/O control request retrieves the capabilities of a USB hub.

<b>IOCTL_USB_GET_HUB_CAPABILITIES_EX</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).



The <b>IOCTL_USB_GET_HUB_CAPABILITIES_EX</b> I/O control request retrieves the capabilities of a USB hub.

<b>IOCTL_USB_GET_HUB_CAPABILITIES_EX</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).



## -ioctlparameters

### -input-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a user-allocated buffer.


### -input-buffer-length
 The buffer length equals <code>sizeof(USB_HUB_CAPABILITIES_EX)</code>.


### -output-buffer
<b>AssociatedIrp.SystemBuffer</b> points to a user-allocated <a href="..\usbioctl\ns-usbioctl-_usb_hub_capabilities_ex.md">USB_HUB_CAPABILITIES_EX</a> structure. On output, this structure describes the hub capabilities. 


### -output-buffer-length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the data that is returned at <b>SystemBuffer</b>, or <code>sizeof(USB_HUB_CAPABILITIES_EX)</code>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES. If the hub has not been started or is not functional, the request returns STATUS_UNSUCCESSFUL.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows Vista and later.

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
</table>

## -see-also
<dl>
<dt>
<a href="..\usbioctl\ns-usbioctl-_usb_hub_capabilities_ex.md">USB_HUB_CAPABILITIES_EX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_USB_GET_HUB_CAPABILITIES_EX control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

