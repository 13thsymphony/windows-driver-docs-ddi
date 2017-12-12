---
UID: NE.udecxusbdevice._UDECX_USB_DEVICE_WAKE_SETTING
title: _UDECX_USB_DEVICE_WAKE_SETTING
author: windows-driver-content
description: Defines values for remote wake capability of a virtual USB device.
old-location: buses\udecx_usb_device_wake_setting.htm
old-project: usbref
ms.assetid: 0CA3B49C-B2A7-497D-A97B-4AC845074BEC
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UDECX_USB_DEVICE_WAKE_SETTING, UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UDECX_USB_DEVICE_WAKE_SETTING
req.alt-loc: UdecxUsbDevice.h
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

# _UDECX_USB_DEVICE_WAKE_SETTING enumeration



## -description
Defines values for remote wake capability of a virtual USB device.



## -syntax

````
typedef enum _UDECX_USB_DEVICE_WAKE_SETTING { 
  UdecxUsbDeviceWakeDisabled       = 0,
  UdecxUsbDeviceWakeEnabled        = ,
  UdecxUsbDeviceWakeNotApplicable  = 
} UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING;
````


## -enum-fields

### -field UdecxUsbDeviceWakeDisabled

The USB device cannot send a wake signal to the host controller.


### -field UdecxUsbDeviceWakeEnabled

The USB device can send a wake signal to the host controller.


### -field UdecxUsbDeviceWakeNotApplicable

This value is used only if the USB device is a SuperSpeed device.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>UdecxUsbDevice.h (include Udecx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_d0_exit.md">EVT_UDECX_USB_DEVICE_D0_EXIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_USB_DEVICE_WAKE_SETTING enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

