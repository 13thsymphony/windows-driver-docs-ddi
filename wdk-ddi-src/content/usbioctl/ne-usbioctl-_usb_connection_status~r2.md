---
UID: NE.usbioctl._USB_CONNECTION_STATUS~r2
title: _USB_CONNECTION_STATUS
author: windows-driver-content
description: The USB_CONNECTION_STATUS enumerator indicates the status of the connection to a device on a USB hub port.
old-location: buses\usb_connection_status.htm
old-project: usbref
ms.assetid: 9006f74f-4033-4f07-816c-380d6d8b3a2d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _USB_CONNECTION_STATUS, USB_CONNECTION_STATUS, *PUSB_CONNECTION_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USB_CONNECTION_STATUS
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
req.irql: 
req.product: Windows 10 or later.
---

# _USB_CONNECTION_STATUS enumeration



## -description
The <b>USB_CONNECTION_STATUS</b> enumerator indicates the status of the connection to a device on a USB hub port.


## -syntax

````
typedef enum _USB_CONNECTION_STATUS { 
  NoDeviceConnected         = 0,
  DeviceConnected           = 1,
  DeviceFailedEnumeration   = 2,
  DeviceGeneralFailure      = 3,
  DeviceCausedOvercurrent   = 4,
  DeviceNotEnoughPower      = 5,
  DeviceNotEnoughBandwidth  = 6,
  DeviceHubNestedTooDeeply  = 7,
  DeviceInLegacyHub         = 8,
  DeviceEnumerating         = 9,
  DeviceReset               = 10
} USB_CONNECTION_STATUS, *PUSB_CONNECTION_STATUS;
````


## -enum-fields

### -field NoDeviceConnected

Indicates that there is no device connected to the port.

### -field DeviceConnected

Indicates that a device was successfully connected to the port.

### -field DeviceFailedEnumeration

Indicates that an attempt was made to connect a device to the port, but the enumeration of the device failed.

### -field DeviceGeneralFailure

Indicates that an attempt was made to connect a device to the port, but the connection failed for unspecified reasons.

### -field DeviceCausedOvercurrent

Indicates that an attempt was made to connect a device to the port, but the attempt failed because of an overcurrent condition.

### -field DeviceNotEnoughPower

Indicates that an attempt was made to connect a device to the port, but there was not enough power to drive the device, and the connection failed.

### -field DeviceNotEnoughBandwidth

Indicates that an attempt was made to connect a device to the port, but there was not enough bandwidth available for the device to function properly, and the connection failed.

### -field DeviceHubNestedTooDeeply

Indicates that an attempt was made to connect a device to the port, but the nesting of USB hubs was too deep, so the connection failed. 

### -field DeviceInLegacyHub

Indicates that an attempt was made to connect a device to the port of an unsupported legacy hub, and the connection failed.

### -field DeviceEnumerating

Indicates that a device connected to the port is currently being enumerated.  
<b>Note</b>  This constant is supported in Windows Vista and later operating systems.

### -field DeviceReset

Indicates that device connected to the port is currently being reset.  
<b>Note</b>  This constant is supported in Windows Vista and later operating systems.

## -remarks
The USB bus driver reports connection status in a <a href="buses.usb_node_connection_information_ex">USB_NODE_CONNECTION_INFORMATION_EX</a> structure in response to an <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a> request.

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
<a href="buses.usb_node_connection_information_ex">USB_NODE_CONNECTION_INFORMATION_EX</a>
</dt>
<dt>
<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a>
</dt>
<dt>
<a href="buses.usb_enumerations">USB Constants and Enumerations</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_CONNECTION_STATUS enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
