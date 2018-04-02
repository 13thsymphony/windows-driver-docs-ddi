---
UID: NE:wdm._DEVICE_RESET_TYPE
title: "_DEVICE_RESET_TYPE"
author: windows-driver-content
description: The DEVICE_RESET_TYPE enumeration specifies the type of device reset that is being requested by a call to the DeviceReset routine of the GUID_DEVICE_RESET_INTERFACE_STANDARD interface.
old-location: kernel\device_reset_type.htm
old-project: kernel
ms.assetid: 598044D9-8B99-453C-96FE-9B04C980BB3A
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: DEVICE_RESET_TYPE, DEVICE_RESET_TYPE enumeration [Kernel-Mode Driver Architecture], FunctionLevelDeviceReset, PlatformLevelDeviceReset, _DEVICE_RESET_TYPE, kernel.device_reset_type, wdm/DEVICE_RESET_TYPE, wdm/FunctionLevelDeviceReset, wdm/PlatformLevelDeviceReset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	DEVICE_RESET_TYPE
product: Windows
targetos: Windows
req.typenames: DEVICE_RESET_TYPE
req.product: Windows 10 or later.
---

# _DEVICE_RESET_TYPE Enumeration
The <b>DEVICE_RESET_TYPE</b> enumeration specifies the type of device reset that is being requested by a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939354">DeviceReset</a> routine of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn928420">GUID_DEVICE_RESET_INTERFACE_STANDARD</a> interface.

## Syntax
```
typedef enum _DEVICE_RESET_TYPE {
  FunctionLevelDeviceReset  ,
  PlatformLevelDeviceReset
} DEVICE_RESET_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>FunctionLevelDeviceReset</td>
                    <td>A function-level device reset, which is restricted to a specific device.</td>
                </tr>
            
                <tr>
                    <td>PlatformLevelDeviceReset</td>
                    <td>A platform-level device reset, which affects a specific device and all other devices that are connected to it via the same power rail or reset line.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn939397">DEVICE_RESET_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939354">DeviceReset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn928420">GUID_DEVICE_RESET_INTERFACE_STANDARD</a>