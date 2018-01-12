---
UID: NI:usbioctl.IOCTL_USB_GET_ROOT_HUB_NAME
title: IOCTL_USB_GET_ROOT_HUB_NAME
author: windows-driver-content
description: The IOCTL_USB_GET_ROOT_HUB_NAME I/O control request is used with the USB_ROOT_HUB_NAME structure to retrieve the symbolic link name of the root hub.IOCTL_USB_GET_ROOT_HUB_NAME is a user-mode I/O control request.
old-location: buses\ioctl_usb_get_root_hub_name.htm
old-project: usbref
ms.assetid: f1d7ab17-516a-4f6e-b343-3f67a6e07ae4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USB_HUB_TYPE, USB_HUB_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_USB_GET_ROOT_HUB_NAME
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

# IOCTL_USB_GET_ROOT_HUB_NAME IOCTL



## -description

The <b>IOCTL_USB_GET_ROOT_HUB_NAME</b> I/O control request is used with the <a href="..\usbioctl\ns-usbioctl-_usb_root_hub_name.md">USB_ROOT_HUB_NAME</a> structure to retrieve the symbolic link name of the root hub.

<b>IOCTL_USB_GET_ROOT_HUB_NAME</b> is a user-mode I/O control request. This request targets the USB host controller (GUID_DEVINTERFACE_USB_HOST_CONTROLLER).



The <b>IOCTL_USB_GET_ROOT_HUB_NAME</b> I/O control request is used with the <a href="..\usbioctl\ns-usbioctl-_usb_root_hub_name.md">USB_ROOT_HUB_NAME</a> structure to retrieve the symbolic link name of the root hub.

<b>IOCTL_USB_GET_ROOT_HUB_NAME</b> is a user-mode I/O control request. This request targets the USB host controller (GUID_DEVINTERFACE_USB_HOST_CONTROLLER).



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
On output, the <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\usbioctl\ns-usbioctl-_usb_root_hub_name.md">USB_ROOT_HUB_NAME</a> structure that contains the symbolic link name of the root hub.  The leading "\xxx\ " text is not included in the retrieved string.


### -output-buffer-length
The size of a <a href="..\usbioctl\ns-usbioctl-_usb_root_hub_name.md">USB_ROOT_HUB_NAME</a> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.

If the root hub is removed or stopped, the request returns STATUS_SUCCESS but the string is NULL. 


## -remarks


## -requirements
<table>
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
<a href="..\usbioctl\ns-usbioctl-_usb_root_hub_name.md">USB_ROOT_HUB_NAME</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_USB_GET_ROOT_HUB_NAME control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

