---
UID: NE:usbspec._USB_DEVICE_SPEED
title: "_USB_DEVICE_SPEED"
author: windows-driver-content
description: The USB_DEVICE_SPEED enumeration defines constants for USB device speeds.
old-location: buses\usb_device_speed.htm
old-project: usbref
ms.assetid: e7c50bac-96ca-446d-a865-4ad87ad5b295
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.usb_device_speed, usbspec/UsbHighSpeed, USB_DEVICE_SPEED enumeration [Buses], UsbFullSpeed, USB_DEVICE_SPEED, usbspec/USB_DEVICE_SPEED, usbstrct_c458b58d-fcfa-4082-bbcf-34e22d504ab9.xml, UsbSuperSpeed, usbspec/UsbSuperSpeed, _USB_DEVICE_SPEED, usbspec/UsbFullSpeed, UsbLowSpeed, usbspec/UsbLowSpeed, UsbHighSpeed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: usbspec.h
req.include-header: Usbspec.h
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
-	Usbspec.h
apiname:
-	USB_DEVICE_SPEED
product: Windows
targetos: Windows
req.typenames: USB_DEVICE_SPEED
req.product: Windows 10 or later.
---

# _USB_DEVICE_SPEED Enumeration
The <b>USB_DEVICE_SPEED</b> enumeration defines constants for USB device speeds.

## Syntax
````
typedef enum  { 
  UsbLowSpeed     = 0,
  UsbFullSpeed  ,
  UsbHighSpeed  ,
  UsbSuperSpeed
} USB_DEVICE_SPEED;
````

## Constants

<table>
            
                <tr>
                    <td>UsbFullSpeed</td>
                    <td>Indicates a full-speed USB 1.1-compliant device.</td>
                </tr>
            
                <tr>
                    <td>UsbHighSpeed</td>
                    <td>Indicates a high-speed USB 2.0-compliant device.</td>
                </tr>
            
                <tr>
                    <td>UsbLowSpeed</td>
                    <td>Indicates a low-speed USB 1.1-compliant device.</td>
                </tr>
            
                <tr>
                    <td>UsbSuperSpeed</td>
                    <td>Indicates a SuperSpeed USB 3.0-compliant device.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbspec.h (include Usbspec.h) |

    ## See Also

        <a href="https://msdn.microsoft.com/library/windows/hardware/ff539322">USB Constants and Enumerations</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USB_DEVICE_SPEED enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>