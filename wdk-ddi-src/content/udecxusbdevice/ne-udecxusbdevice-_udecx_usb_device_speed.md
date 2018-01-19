---
UID : NE:udecxusbdevice._UDECX_USB_DEVICE_SPEED
title : _UDECX_USB_DEVICE_SPEED
author : windows-driver-content
description : Defines values for USB device speeds.
old-location : buses\udecx_usb_device_speed.htm
old-project : usbref
ms.assetid : 337C9FFE-F97A-4F0F-9567-D1FF532FE165
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _UDECX_USB_DEVICE_SPEED, *PUDECX_USB_DEVICE_SPEED, UDECX_USB_DEVICE_SPEED
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : udecxusbdevice.h
req.include-header : Udecx.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : UDECX_USB_DEVICE_SPEED
req.alt-loc : UdecxUsbDevice.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : "*PUDECX_USB_DEVICE_SPEED, UDECX_USB_DEVICE_SPEED"
req.product : Windows 10 or later.
---

# _UDECX_USB_DEVICE_SPEED Enumeration
Defines values for USB device speeds.

## Syntax
````
typedef enum _UDECX_USB_DEVICE_SPEED { 
  UdecxUsbLowSpeed    = 0,
  UdecxUsbFullSpeed   = ,
  UdecxUsbHighSpeed   = ,
  UdecxUsbSuperSpeed  = 
} UDECX_USB_DEVICE_SPEED;
````

## Constants

<table>

<tr>
<td>UdecxUsbFullSpeed</td>
<td>Indicates a full-speed USB 1.1-compliant device.</td>
</tr>

<tr>
<td>UdecxUsbHighSpeed</td>
<td>Indicates a high-speed USB 2.0-compliant device.</td>
</tr>

<tr>
<td>UdecxUsbLowSpeed</td>
<td>Indicates a low-speed USB 1.1-compliant device.</td>
</tr>

<tr>
<td>UdecxUsbSuperSpeed</td>
<td>Indicates a SuperSpeed USB 3.0-compliant device.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | udecxusbdevice.h (include Udecx.h) |

## See Also

<dl>
<dt>
<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitsetspeed.md">UdecxUsbDeviceInitSetSpeed</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_USB_DEVICE_SPEED enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>