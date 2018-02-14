---
UID: NE:usbioctl._USB_CONNECTION_STATUS
title: "_USB_CONNECTION_STATUS"
author: windows-driver-content
description: The USB_CONNECTION_STATUS enumerator indicates the status of the connection to a device on a USB hub port.
old-location: buses\usb_connection_status.htm
old-project: usbref
ms.assetid: 9006f74f-4033-4f07-816c-380d6d8b3a2d
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: DeviceNotEnoughPower, DeviceReset, NoDeviceConnected, DeviceCausedOvercurrent, DeviceHubNestedTooDeeply, usbioctl/DeviceHubNestedTooDeeply, DeviceFailedEnumeration, usbioctl/NoDeviceConnected, usbioctl/DeviceNotEnoughBandwidth, USB_CONNECTION_STATUS enumeration [Buses], usbioctl/DeviceGeneralFailure, _USB_CONNECTION_STATUS, usbioctl/USB_CONNECTION_STATUS, usbioctl/DeviceInLegacyHub, usbstrct_3f747b8b-9fe5-48f1-bfc4-3701ab8be8e9.xml, usbioctl/DeviceNotEnoughPower, PUSB_CONNECTION_STATUS, DeviceGeneralFailure, buses.usb_connection_status, USB_CONNECTION_STATUS, usbioctl/DeviceFailedEnumeration, usbioctl/DeviceReset, usbioctl/DeviceEnumerating, usbioctl/PUSB_CONNECTION_STATUS, DeviceConnected, DeviceInLegacyHub, DeviceNotEnoughBandwidth, usbioctl/DeviceConnected, PUSB_CONNECTION_STATUS enumeration pointer [Buses], usbioctl/DeviceCausedOvercurrent, DeviceEnumerating, *PUSB_CONNECTION_STATUS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbioctl.h
apiname:
-	USB_CONNECTION_STATUS
product: Windows
targetos: Windows
req.typenames: "*PUSB_CONNECTION_STATUS, USB_CONNECTION_STATUS"
req.product: Windows 10 or later.
---

# _USB_CONNECTION_STATUS Enumeration
The <b>USB_CONNECTION_STATUS</b> enumerator indicates the status of the connection to a device on a USB hub port.

## Syntax
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

## Constants

<table>
            
                <tr>
                    <td>DeviceCausedOvercurrent</td>
                    <td>Indicates that an attempt was made to connect a device to the port, but the attempt failed because of an overcurrent condition.</td>
                </tr>
            
                <tr>
                    <td>DeviceConnected</td>
                    <td>Indicates that a device was successfully connected to the port.</td>
                </tr>
            
                <tr>
                    <td>DeviceEnumerating</td>
                    <td>Indicates that a device connected to the port is currently being enumerated.  

<b>Note</b>  This constant is supported in Windows Vista and later operating systems.</td>
                </tr>
            
                <tr>
                    <td>DeviceFailedEnumeration</td>
                    <td>Indicates that an attempt was made to connect a device to the port, but the enumeration of the device failed.</td>
                </tr>
            
                <tr>
                    <td>DeviceGeneralFailure</td>
                    <td>Indicates that an attempt was made to connect a device to the port, but the connection failed for unspecified reasons.</td>
                </tr>
            
                <tr>
                    <td>DeviceHubNestedTooDeeply</td>
                    <td>Indicates that an attempt was made to connect a device to the port, but the nesting of USB hubs was too deep, so the connection failed.</td>
                </tr>
            
                <tr>
                    <td>DeviceInLegacyHub</td>
                    <td>Indicates that an attempt was made to connect a device to the port of an unsupported legacy hub, and the connection failed.</td>
                </tr>
            
                <tr>
                    <td>DeviceNotEnoughBandwidth</td>
                    <td>Indicates that an attempt was made to connect a device to the port, but there was not enough bandwidth available for the device to function properly, and the connection failed.</td>
                </tr>
            
                <tr>
                    <td>DeviceNotEnoughPower</td>
                    <td>Indicates that an attempt was made to connect a device to the port, but there was not enough power to drive the device, and the connection failed.</td>
                </tr>
            
                <tr>
                    <td>DeviceReset</td>
                    <td>Indicates that device connected to the port is currently being reset.  

<b>Note</b>  This constant is supported in Windows Vista and later operating systems.</td>
                </tr>
            
                <tr>
                    <td>NoDeviceConnected</td>
                    <td>Indicates that there is no device connected to the port.</td>
                </tr>
</table>

    ## Remarks

        The USB bus driver reports connection status in a <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_information_ex.md">USB_NODE_CONNECTION_INFORMATION_EX</a> structure in response to an <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbioctl.h (include Usbioctl.h) |

    ## See Also

        <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_information_ex.md">USB_NODE_CONNECTION_INFORMATION_EX</a>



<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_CONNECTION_STATUS enumeration%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>