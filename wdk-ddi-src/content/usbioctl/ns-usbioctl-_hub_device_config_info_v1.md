---
UID: NS.USBIOCTL._HUB_DEVICE_CONFIG_INFO_V1
title: _HUB_DEVICE_CONFIG_INFO_V1
author: windows-driver-content
description: The HUB_DEVICE_CONFIG_INFO structure is used in conjunction with the kernel-mode IOCTL, IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO to request to report information about a USB device and the hub to which the device is attached.
old-location: buses\hub_device_config_info.htm
old-project: usbref
ms.assetid: 2e94cf01-6edf-40ca-b25e-ce7c125e4686
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _HUB_DEVICE_CONFIG_INFO_V1, *PHUB_DEVICE_CONFIG_INFO, HUB_DEVICE_CONFIG_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows XP and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HUB_DEVICE_CONFIG_INFO
req.alt-loc: usbioctl.h
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

# _HUB_DEVICE_CONFIG_INFO_V1 structure



## -description
The <b>HUB_DEVICE_CONFIG_INFO</b> structure is used in conjunction with the kernel-mode IOCTL, <a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_get_device_config_info.md">IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO</a> to request to report information about a USB device and the hub to which the device is attached. 


## -syntax

````
typedef struct _HUB_DEVICE_CONFIG_INFO {
  ULONG              Version;
  ULONG              Length;
  USB_HUB_CAP_FLAGS  HubFlags;
  USB_ID_STRING      HardwareIds;
  USB_ID_STRING      CompatibleIds;
  USB_ID_STRING      DeviceDescription;
} HUB_DEVICE_CONFIG_INFO, *PHUB_DEVICE_CONFIG_INFO;
````


## -struct-fields

### -field Version

Specifies the version number.  Must be set to 1. 

### -field Length

Specifies the size of the <b>HUB_DEVICE_CONFIG_INFO</b> structure. Must be set by the caller.

### -field HubFlags

Specifies the hub capabilities in a <a href="buses.usb_hub_cap_flags">USB_HUB_CAP_FLAGS</a> structure.  

### -field HardwareIds

The PnP hardware ID multi-string for the USB device in a <a href="buses.usb_id_string">USB_ID_STRING</a> structure. 

### -field CompatibleIds

 PnP compatible ID multi-string for the USB device in a <a href="buses.usb_id_string">USB_ID_STRING</a> structure. 

### -field DeviceDescription

Description of the device in a <a href="buses.usb_id_string">USB_ID_STRING</a> structure. This may be set to <b>NULL</b>.

## -remarks

 The <b>Buffer</b> member of the <a href="buses.usb_id_string">USB_ID_STRING</a> structure points to a string that contains <b>HardwareIds</b>, <b>CompatibleIds</b>, and <b>DeviceDescription</b> values.
The caller is responsible for releasing this string buffer, which is allocated by the hub driver.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows XP and later operating systems.
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
<a href="..\usbioctl\ni-usbioctl-ioctl_internal_usb_get_device_config_info.md">IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO</a>
</dt>
<dt>
<a href="buses.usb_hub_cap_flags">USB_HUB_CAP_FLAGS</a>
</dt>
<dt>
<a href="buses.usb_id_string">USB_ID_STRING</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20HUB_DEVICE_CONFIG_INFO structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
