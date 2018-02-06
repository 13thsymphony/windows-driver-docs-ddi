---
UID: NE:udecxusbdevice._UDECX_ENDPOINTS_CONFIGURE_TYPE
title: "_UDECX_ENDPOINTS_CONFIGURE_TYPE"
author: windows-driver-content
description: Defines values for endpoint configuration options.
old-location: buses\udecx_endpoints_configure_type.htm
old-project: usbref
ms.assetid: F13C7D8D-C134-432A-904B-7435894B07E5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PUDECX_ENDPOINTS_CONFIGURE_TYPE, udecxusbdevice/PUDECX_ENDPOINTS_CONFIGURE_TYPE, buses.udecx_endpoints_configure_type, udecxusbdevice/UdecxEndpointsConfigureTypeDeviceConfigurationChange, UdecxEndpointsConfigureTypeEndpointsReleasedOnly, *PUDECX_ENDPOINTS_CONFIGURE_TYPE, PUDECX_ENDPOINTS_CONFIGURE_TYPE enumeration pointer [Buses], udecxusbdevice/UdecxEndpointsConfigureTypeEndpointsReleasedOnly, udecxusbdevice/UdecxEndpointsConfigureTypeInterfaceSettingChange, udecxusbdevice/UdecxEndpointsConfigureTypeDeviceInitialize, _UDECX_ENDPOINTS_CONFIGURE_TYPE, udecxusbdevice/UDECX_ENDPOINTS_CONFIGURE_TYPE, UdecxEndpointsConfigureTypeDeviceInitialize, UdecxEndpointsConfigureTypeDeviceConfigurationChange, UDECX_ENDPOINTS_CONFIGURE_TYPE, UDECX_ENDPOINTS_CONFIGURE_TYPE enumeration [Buses], UdecxEndpointsConfigureTypeInterfaceSettingChange
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	udecxusbdevice.h
apiname:
-	UDECX_ENDPOINTS_CONFIGURE_TYPE
product: Windows
targetos: Windows
req.typenames: "*PUDECX_ENDPOINTS_CONFIGURE_TYPE, UDECX_ENDPOINTS_CONFIGURE_TYPE"
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
                    <td>UdecxEndpointsConfigureTypeDeviceConfigurationChange</td>
                    <td>The requested change applies to the USB device configuration.</td>
                </tr>
            
                <tr>
                    <td>UdecxEndpointsConfigureTypeDeviceInitialize</td>
                    <td>Reserved for internal use.</td>
                </tr>
            
                <tr>
                    <td>UdecxEndpointsConfigureTypeEndpointsReleasedOnly</td>
                    <td>The requested change applies to an endpoint of an interface setting.</td>
                </tr>
            
                <tr>
                    <td>UdecxEndpointsConfigureTypeInterfaceSettingChange</td>
                    <td>The requested change applies to an alternate setting of a USB interface.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | udecxusbdevice.h (include Udecx.h) |

    ## See Also

        <a href="..\udecxusbdevice\ns-udecxusbdevice-_udecx_endpoints_configure_params.md">UDECX_ENDPOINTS_CONFIGURE_PARAMS</a>

<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md">EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UDECX_ENDPOINTS_CONFIGURE_TYPE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>