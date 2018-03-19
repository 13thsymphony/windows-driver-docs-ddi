---
UID: NE:udecxusbdevice._UDECX_ENDPOINTS_CONFIGURE_TYPE
title: "_UDECX_ENDPOINTS_CONFIGURE_TYPE"
author: windows-driver-content
description: Defines values for endpoint configuration options.
old-location: buses\udecx_endpoints_configure_type.htm
old-project: usbref
ms.assetid: F13C7D8D-C134-432A-904B-7435894B07E5
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUDECX_ENDPOINTS_CONFIGURE_TYPE, PUDECX_ENDPOINTS_CONFIGURE_TYPE, PUDECX_ENDPOINTS_CONFIGURE_TYPE enumeration pointer [Buses], UDECX_ENDPOINTS_CONFIGURE_TYPE, UDECX_ENDPOINTS_CONFIGURE_TYPE enumeration [Buses], UdecxEndpointsConfigureTypeDeviceConfigurationChange, UdecxEndpointsConfigureTypeDeviceInitialize, UdecxEndpointsConfigureTypeEndpointsReleasedOnly, UdecxEndpointsConfigureTypeInterfaceSettingChange, _UDECX_ENDPOINTS_CONFIGURE_TYPE, buses.udecx_endpoints_configure_type, udecxusbdevice/PUDECX_ENDPOINTS_CONFIGURE_TYPE, udecxusbdevice/UDECX_ENDPOINTS_CONFIGURE_TYPE, udecxusbdevice/UdecxEndpointsConfigureTypeDeviceConfigurationChange, udecxusbdevice/UdecxEndpointsConfigureTypeDeviceInitialize, udecxusbdevice/UdecxEndpointsConfigureTypeEndpointsReleasedOnly, udecxusbdevice/UdecxEndpointsConfigureTypeInterfaceSettingChange"
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	udecxusbdevice.h
api_name:
-	UDECX_ENDPOINTS_CONFIGURE_TYPE
product: Windows
targetos: Windows
req.typenames: UDECX_ENDPOINTS_CONFIGURE_TYPE, *PUDECX_ENDPOINTS_CONFIGURE_TYPE
req.product: Windows 10 or later.
---

# _UDECX_ENDPOINTS_CONFIGURE_TYPE Enumeration
Defines values for endpoint configuration options.

## Syntax
````
typedef enum _UDECX_ENDPOINTS_CONFIGURE_TYPE { 
  UdecxEndpointsConfigureTypeDeviceInitialize           = 0,
  UdecxEndpointsConfigureTypeDeviceConfigurationChange  = ,
  UdecxEndpointsConfigureTypeInterfaceSettingChange     = ,
  UdecxEndpointsConfigureTypeEndpointsReleasedOnly      = 
} UDECX_ENDPOINTS_CONFIGURE_TYPE, *PUDECX_ENDPOINTS_CONFIGURE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>UdecxEndpointsConfigureTypeDeviceInitialize</td>
                    <td>Reserved for internal use.</td>
                </tr>
            
                <tr>
                    <td>UdecxEndpointsConfigureTypeDeviceConfigurationChange</td>
                    <td>The requested change applies to the USB device configuration.</td>
                </tr>
            
                <tr>
                    <td>UdecxEndpointsConfigureTypeInterfaceSettingChange</td>
                    <td>The requested change applies to an alternate setting of a USB interface.</td>
                </tr>
            
                <tr>
                    <td>UdecxEndpointsConfigureTypeEndpointsReleasedOnly</td>
                    <td>The requested change applies to an endpoint of an interface setting.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | udecxusbdevice.h (include Udecx.h) |

## See Also

<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>



<a href="..\udecxusbdevice\ns-udecxusbdevice-_udecx_endpoints_configure_params.md">UDECX_ENDPOINTS_CONFIGURE_PARAMS</a>