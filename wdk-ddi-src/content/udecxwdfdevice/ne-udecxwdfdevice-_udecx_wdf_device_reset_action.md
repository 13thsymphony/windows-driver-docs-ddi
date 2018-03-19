---
UID: NE:udecxwdfdevice._UDECX_WDF_DEVICE_RESET_ACTION
title: "_UDECX_WDF_DEVICE_RESET_ACTION"
author: windows-driver-content
description: Defines values that indicate the types of reset operation supported by an emulated USB host controller.
old-location: buses\udecx_wdf_device_reset_action.htm
old-project: usbref
ms.assetid: E3216F62-5506-4DA2-AD89-B2406D3E97C0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUDECX_WDF_DEVICE_RESET_ACTION, UDECX_WDF_DEVICE_RESET_ACTION, UDECX_WDF_DEVICE_RESET_ACTION enumeration [Buses], UdecxWdfDeviceResetActionResetEachUsbDevice, UdecxWdfDeviceResetActionResetWdfDevice, _UDECX_WDF_DEVICE_RESET_ACTION, buses.udecx_wdf_device_reset_action, udecxwdfdevice/UDECX_WDF_DEVICE_RESET_ACTION, udecxwdfdevice/UdecxWdfDeviceResetActionResetEachUsbDevice, udecxwdfdevice/UdecxWdfDeviceResetActionResetWdfDevice"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: udecxwdfdevice.h
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
-	UdecxWdfDevice.h
api_name:
-	UDECX_WDF_DEVICE_RESET_ACTION
product: Windows
targetos: Windows
req.typenames: UDECX_WDF_DEVICE_RESET_ACTION, *PUDECX_WDF_DEVICE_RESET_ACTION
req.product: Windows 10 or later.
---

# _UDECX_WDF_DEVICE_RESET_ACTION Enumeration
Defines values that indicate the types of reset operation supported by an emulated USB host controller.

## Syntax
````
typedef enum _UDECX_WDF_DEVICE_RESET_ACTION { 
  UdecxWdfDeviceResetActionResetEachUsbDevice  = 0,
  UdecxWdfDeviceResetActionResetWdfDevice      = 
} UDECX_WDF_DEVICE_RESET_ACTION;
````

## Constants

<table>
            
                <tr>
                    <td>UdecxWdfDeviceResetActionResetEachUsbDevice</td>
                    <td>Each device that is attached to the controller is reset.</td>
                </tr>
            
                <tr>
                    <td>UdecxWdfDeviceResetActionResetWdfDevice</td>
                    <td>The emulated host controller is reset.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | udecxwdfdevice.h (include Udecx.h) |

## See Also

<a href="..\udecxwdfdevice\ns-udecxwdfdevice-_udecx_wdf_device_config.md">UDECX_WDF_DEVICE_CONFIG</a>



<a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt_udecx_wdf_device_reset.md">EVT_UDECX_WDF_DEVICE_RESET</a>