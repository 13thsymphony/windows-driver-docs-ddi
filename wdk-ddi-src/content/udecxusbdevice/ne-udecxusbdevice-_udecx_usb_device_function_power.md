---
UID : NE:udecxusbdevice._UDECX_USB_DEVICE_FUNCTION_POWER
title : "_UDECX_USB_DEVICE_FUNCTION_POWER"
author : windows-driver-content
description : Defines values for function wake capability of a virtual USB 3.0 device.
old-location : buses\udecx_usb_device_function_power.htm
old-project : usbref
ms.assetid : 7EE6D8AE-E001-4BC9-A617-682202A297E7
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PUDECX_USB_DEVICE_FUNCTION_POWER enumeration pointer [Buses], UdecxUsbDeviceFunctionNotSuspended, udecxusbdevice/UdecxUsbDeviceFunctionNotSuspended, UDECX_USB_DEVICE_FUNCTION_POWER enumeration [Buses], udecxusbdevice/PUDECX_USB_DEVICE_FUNCTION_POWER, UdecxUsbDeviceFunctionSuspendedCannotWake, udecxusbdevice/UdecxUsbDeviceFunctionSuspendedCanWake, udecxusbdevice/UdecxUsbDeviceFunctionSuspendedCannotWake, _UDECX_USB_DEVICE_FUNCTION_POWER, UdecxUsbDeviceFunctionSuspendedCanWake, PUDECX_USB_DEVICE_FUNCTION_POWER, buses.udecx_usb_device_function_power, *PUDECX_USB_DEVICE_FUNCTION_POWER, UDECX_USB_DEVICE_FUNCTION_POWER, udecxusbdevice/UDECX_USB_DEVICE_FUNCTION_POWER
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : UDECX_USB_DEVICE_FUNCTION_POWER, *PUDECX_USB_DEVICE_FUNCTION_POWER
req.product : Windows 10 or later.
---

# _UDECX_USB_DEVICE_FUNCTION_POWER Enumeration
Defines values for function wake capability of a virtual USB 3.0  device.

## Syntax
````
typedef enum _UDECX_USB_DEVICE_FUNCTION_POWER { 
  UdecxUsbDeviceFunctionNotSuspended         = 0,
  UdecxUsbDeviceFunctionSuspendedCannotWake  = ,
  UdecxUsbDeviceFunctionSuspendedCanWake     = 
} UDECX_USB_DEVICE_FUNCTION_POWER, *PUDECX_USB_DEVICE_FUNCTION_POWER;
````

## Constants

<table>

<tr>
<td>UdecxUsbDeviceFunctionNotSuspended</td>
<td>The USB interface cannot enter function suspend.</td>
</tr>

<tr>
<td>UdecxUsbDeviceFunctionSuspendedCannotWake</td>
<td>The USB interface cannot send a wake signal to the host controller.</td>
</tr>

<tr>
<td>UdecxUsbDeviceFunctionSuspendedCanWake</td>
<td>The USB interface can send a wake signal to the host controller when the function is in suspend state.</td>
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

<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_set_function_suspend_and_wake.md">EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_USB_DEVICE_FUNCTION_POWER enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>