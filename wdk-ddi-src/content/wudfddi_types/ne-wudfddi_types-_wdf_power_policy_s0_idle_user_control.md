---
UID : NE:wudfddi_types._WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
title : "_WDF_POWER_POLICY_S0_IDLE_USER_CONTROL"
author : windows-driver-content
description : The WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration identifies whether a user can control a device's behavior when the device is idle and the system is in its working (S0) state.
old-location : wdf\wdf_power_policy_s0_idle_user_control.htm
old-project : wdf
ms.assetid : ee51c436-2d1c-49d0-ab76-337317eeeeda
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdfdevice/IdleAllowUserControl, wudfddi_types/IdleAllowUserControl, WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration, wdfdevice/IdleUserControlInvalid, kmdf.wdf_power_policy_s0_idle_user_control, WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, wudfddi_types/IdleUserControlInvalid, IdleDoNotAllowUserControl, wdf.wdf_power_policy_s0_idle_user_control, wudfddi_types/WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, IdleUserControlInvalid, _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, wdfdevice/WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, wudfddi_types/IdleDoNotAllowUserControl, DFDeviceObjectGeneralRef_3d85e623-4e88-4e66-a21d-489aebd13ddf.xml, wdfdevice/IdleDoNotAllowUserControl, IdleAllowUserControl
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wudfddi_types.h
req.include-header : Wdf.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 1.11
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
req.product : Windows 10 or later.
---

# _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</b> enumeration identifies whether a user can control a device's behavior when the device is idle and the system is in its working (S0) state.

## Syntax
````
typedef enum _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL { 
  IdleUserControlInvalid     = 0,
  IdleDoNotAllowUserControl  = 1,
  IdleAllowUserControl       = 2
} WDF_POWER_POLICY_S0_IDLE_USER_CONTROL;
````

## Constants

<table>

<tr>
<td>IdleAllowUserControl</td>
<td>Users can control the device's idle behavior.</td>
</tr>

<tr>
<td>IdleDoNotAllowUserControl</td>
<td>Users cannot control the device's idle behavior.</td>
</tr>

<tr>
<td>IdleUserControlInvalid</td>
<td>For internal use only.</td>
</tr>
</table>

## Remarks

The <b>WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</b> enumeration is used as a member type in the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

Users control a device's idle behavior by modifying information on a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/user-control-of-device-idle-and-wake-behavior">property sheet</a>. The framework creates the property sheet and Device Manager displays it.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 1.11 |
| **Header** | wudfddi_types.h (include Wdf.h) |

## See Also

<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>