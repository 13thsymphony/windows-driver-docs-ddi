---
UID: NI.usbioctl.IOCTL_USB_GET_DEVICE_CHARACTERISTICS
title: IOCTL_USB_GET_DEVICE_CHARACTERISTICS
author: windows-driver-content
description: The client driver sends this request to determine general characteristics about a USB device, such as maximum send and receive delays for any request.
old-location: buses\_ioctl_usb_get_device_characteristics.htm
old-project: usbref
ms.assetid: FEEF13FE-E7CF-4513-8E16-B1E46283883C
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USB_HUB_TYPE, USB_HUB_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_USB_GET_DEVICE_CHARACTERISTICS
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
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_DEVICE_CHARACTERISTICS IOCTL



## -description
The client driver sends this request to determine general characteristics about a USB device, such as maximum send and receive delays for any request.



## -ioctlparameters

### -input-buffer

<text></text>

### -input-buffer-length

<text></text>

### -output-buffer

<text></text>

### -output-buffer-length
The <b>AssociatedIrp.SystemBuffer</b> member is a pointer to a caller-allocated <a href="buses.usb_device_characteristics">USB_DEVICE_CHARACTERISTIC</a>S structure.  On input, set <b>Version</b> to USB_DEVICE_CHARACTERISTICS_VERSION_1. On output <b>Version</b> is reset to a version less than or equal to USB_DEVICE_CHARACTERISTICS_VERSION_1;  <b>UsbDeviceCharacteristicsFlags</b> is set to USB_DEVICE_CHARACTERISTICS_MAXIMUM_PATH_DELAYS_AVAILABLE and the remaining members of the structure is filled with delay information.

The size of the <a href="buses.usb_device_characteristics">USB_DEVICE_CHARACTERISTICS</a> structure.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> indicates  the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbioctl.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>
</dt>
<dt>
<a href="wdf.wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>
</dt>
<dt>
<a href="wdf.wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>
</dt>
<dt>
<a href="wdf.wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
</dt>
<dt><a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/usb-client-drivers-for-ma-usb">USB client drivers for Media-Agnostic (MA-USB)</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20 IOCTL_USB_GET_DEVICE_CHARACTERISTICS control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

