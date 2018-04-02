---
UID: NE:wdfdevice._WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
title: "_WDF_POWER_POLICY_S0_IDLE_USER_CONTROL"
author: windows-driver-content
description: The WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration identifies whether a user can control a device's behavior when the device is idle and the system is in its working (S0) state.
old-location: wdf\wdf_power_policy_s0_idle_user_control.htm
old-project: wdf
ms.assetid: ee51c436-2d1c-49d0-ab76-337317eeeeda
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_3d85e623-4e88-4e66-a21d-489aebd13ddf.xml, IdleAllowUserControl, IdleDoNotAllowUserControl, IdleUserControlInvalid, WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration, _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, kmdf.wdf_power_policy_s0_idle_user_control, wdf.wdf_power_policy_s0_idle_user_control, wdfdevice/IdleAllowUserControl, wdfdevice/IdleDoNotAllowUserControl, wdfdevice/IdleUserControlInvalid, wdfdevice/WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, wudfddi_types/IdleAllowUserControl, wudfddi_types/IdleDoNotAllowUserControl, wudfddi_types/IdleUserControlInvalid, wudfddi_types/WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
-	wudfddi_types.h
api_name:
-	WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
product: Windows
targetos: Windows
req.typenames: WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
req.product: Windows 10 or later.
---

# _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</b> enumeration identifies whether a user can control a device's behavior when the device is idle and the system is in its working (S0) state.

## Syntax
```
typedef enum _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL {
  IdleUserControlInvalid     ,
  IdleDoNotAllowUserControl  ,
  IdleAllowUserControl
} WDF_POWER_POLICY_S0_IDLE_USER_CONTROL;
```

## Constants

<table>
            
                <tr>
                    <td>IdleUserControlInvalid</td>
                    <td>For internal use only.</td>
                </tr>
            
                <tr>
                    <td>IdleDoNotAllowUserControl</td>
                    <td>Users cannot control the device's idle behavior.</td>
                </tr>
            
                <tr>
                    <td>IdleAllowUserControl</td>
                    <td>Users can control the device's idle behavior.</td>
                </tr>
</table>

## Remarks

The <b>WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</b> enumeration is used as a member type in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

Users control a device's idle behavior by modifying information on a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior">property sheet</a>. The framework creates the property sheet and Device Manager displays it.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 1.11 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>