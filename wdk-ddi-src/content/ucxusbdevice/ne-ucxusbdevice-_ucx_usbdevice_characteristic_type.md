---
UID: NE:ucxusbdevice._UCX_USBDEVICE_CHARACTERISTIC_TYPE
title: "_UCX_USBDEVICE_CHARACTERISTIC_TYPE"
author: windows-driver-content
description: Defines values that indicates the type of device characteristic.
old-location: buses\ucx_usbdevice_characteristic_type.htm
old-project: usbref
ms.assetid: 86FA72CC-C23F-40B9-9FDD-80C3B0D5EA73
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PUCX_USBDEVICE_CHARACTERISTIC_TYPE, PUCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration pointer [Buses], UCX_USBDEVICE_CHARACTERISTIC_TYPE, UCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration [Buses], UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY, _UCX_USBDEVICE_CHARACTERISTIC_TYPE, buses.ucx_usbdevice_characteristic_type, ucxusbdevice/PUCX_USBDEVICE_CHARACTERISTIC_TYPE, ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC_TYPE, ucxusbdevice/UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxusbdevice.h
api_name:
-	UCX_USBDEVICE_CHARACTERISTIC_TYPE
product:
- Windows
targetos: Windows
req.typenames: UCX_USBDEVICE_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---

# _UCX_USBDEVICE_CHARACTERISTIC_TYPE Enumeration
Defines values that indicates the type of device characteristic.

## Syntax
```
typedef enum _UCX_USBDEVICE_CHARACTERISTIC_TYPE {
  UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY
} UCX_USBDEVICE_CHARACTERISTIC_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>UCX_USBDEVICE_CHARACTERISTIC_TYPE_PATH_DELAY</td>
                    <td>The type of characteristic of the device.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |

## See Also

<a href="https://msdn.microsoft.com/EE8568F6-3D88-477E-9F0D-044D014EBCF3">EVT_UCX_USBDEVICE_GET_CHARACTERISTIC</a>



<a href="https://msdn.microsoft.com/31BF5607-51EA-4FBF-A754-872FBD45915D">UCX_USBDEVICE_CHARACTERISTIC</a>