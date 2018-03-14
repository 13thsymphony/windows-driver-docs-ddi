---
UID: NE:ntpoapi._POWER_STATE_TYPE
title: "_POWER_STATE_TYPE"
author: windows-driver-content
description: The POWER_STATE_TYPE enumeration type indicates that a power state value is a system power state or a device power state.
old-location: kernel\power_state_type.htm
old-project: kernel
ms.assetid: d0e97474-4119-4359-a9f9-644c82df7fab
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPOWER_STATE_TYPE, DevicePowerState, POWER_STATE_TYPE, POWER_STATE_TYPE enumeration [Kernel-Mode Driver Architecture], PPOWER_STATE_TYPE, PPOWER_STATE_TYPE enumeration pointer [Kernel-Mode Driver Architecture], SystemPowerState, _POWER_STATE_TYPE, kernel.power_state_type, sysenum_bdfdaea1-ec64-4b74-96d0-95641797ebb4.xml, wdm/DevicePowerState, wdm/POWER_STATE_TYPE, wdm/PPOWER_STATE_TYPE, wdm/SystemPowerState"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntpoapi.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ntpoapi.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	POWER_STATE_TYPE
product: Windows
targetos: Windows
req.typenames: POWER_STATE_TYPE, *PPOWER_STATE_TYPE
---

# _POWER_STATE_TYPE Enumeration
The <b>POWER_STATE_TYPE</b> enumeration type indicates that a power state value is a system power state or a device power state.

## Syntax
````
typedef enum _POWER_STATE_TYPE { 
  SystemPowerState  = 0,
  DevicePowerState  = 1
} POWER_STATE_TYPE, *PPOWER_STATE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>DevicePowerState</td>
                    <td>Indicates a <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a> value.</td>
                </tr>
            
                <tr>
                    <td>SystemPowerState</td>
                    <td>Indicates a <a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a> value.</td>
                </tr>
</table>

## Remarks

The <b>POWER_STATE_TYPE</b> enumeration type is used in conjunction with a value of type <a href="..\wdm\ns-wdm-_power_state.md">POWER_STATE</a> to indicate that the power state value is a system power state value or a device power state value. For an example, see <a href="..\wdm\nf-wdm-posetpowerstate.md">PoSetPowerState</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntpoapi.h (include Wdm.h, Ntddk.h, Ntifs.h, Ntpoapi.h) |

## See Also

<a href="..\wdm\ns-wdm-_power_state.md">POWER_STATE</a>



<a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>



<a href="..\wdm\nf-wdm-posetpowerstate.md">PoSetPowerState</a>



<a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POWER_STATE_TYPE enumeration%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>