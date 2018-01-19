---
UID : NF:udecxusbdevice.UdecxUsbDeviceInitSetEndpointsType
title : UdecxUsbDeviceInitSetEndpointsType function
author : windows-driver-content
description : Indicates the type of endpoint (simple or dynamic) in the initialization parameters that the client driver uses to create the virtual USB device.
old-location : buses\udecxusbdeviceinitsetendpointstype.htm
old-project : usbref
ms.assetid : 44760191-77DD-40A9-AA11-AE8AB55AB307
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : UdecxUsbDeviceInitSetEndpointsType
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : udecxusbdevice.h
req.include-header : Udecx.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 1.15
req.umdf-ver : 
req.alt-api : UdecxUsbDeviceInitSetEndpointsType
req.alt-loc : Udecxstub.lib,Udecxstub.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Udecxstub.lib
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : "*PUDECX_USB_DEVICE_WAKE_SETTING, UDECX_USB_DEVICE_WAKE_SETTING"
req.product : Windows 10 or later.
---


# UdecxUsbDeviceInitSetEndpointsType function
Indicates the type of endpoint (simple or dynamic) in the initialization parameters that the client driver uses to create the virtual USB device.

## Syntax

````
void UdecxUsbDeviceInitSetEndpointsType(
  _Inout_ PUDECXUSBDEVICE_INIT UdecxUsbDeviceInit,
  _In_    UDECX_ENDPOINT_TYPE  UdecxEndpointType
);
````

## Parameters

`UdecxUsbDeviceInit`

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>.

`UdecxEndpointType`

A <a href="..\udecxusbdevice\ne-udecxusbdevice-_udecx_endpoint_type.md">UDECX_ENDPOINT_TYPE</a>-type value that indicates the type of USB endpoint.


## Return Value

This function does not return a value.

## Remarks

Before creating the virtual USB device, the client driver must indicate the type of endpoint it supports. It can support one of two types (defined in <a href="..\udecxusbdevice\ne-udecxusbdevice-_udecx_endpoint_type.md">UDECX_ENDPOINT_TYPE</a>): 

The <i>UdecxUsbDeviceInit</i> is an opaque structure that contains pointers to callback functions related to endpoints. If the client driver supports dynamic endpoints, then these callback functions must be implemented by the driver:

Before calling this method, the client driver must have set those pointers by calling <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks.md">UdecxUsbDeviceInitSetStateChangeCallbacks</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** |  |
| **Header** | udecxusbdevice.h (include Udecx.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/4DABCC96-F3F5-43D9-9BCF-A2663ED30137">USB endpoints</a>
</dt>
<dt>
<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>
</dt>
<dt>
<a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks.md">UdecxUsbDeviceInitSetStateChangeCallbacks</a>
</dt>
<dt>
<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceInitSetEndpointsType function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>