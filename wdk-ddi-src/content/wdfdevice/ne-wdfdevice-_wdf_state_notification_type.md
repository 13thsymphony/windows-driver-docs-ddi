---
UID: NE:wdfdevice._WDF_STATE_NOTIFICATION_TYPE
title: "_WDF_STATE_NOTIFICATION_TYPE"
author: windows-driver-content
description: The WDF_STATE_NOTIFICATION_TYPE enumeration identifies the type of Plug and Play, power, or power policy notification that a framework-based driver will receive.
old-location: wdf\wdf_state_notification_type.htm
old-project: wdf
ms.assetid: fc44c970-482c-4fbf-a149-e6b732f6c9d8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_c1bdabfc-dd89-4eeb-b5ba-9f03a65414c5.xml, StateNotificationAllStates, StateNotificationEnterState, StateNotificationInvalid, StateNotificationLeaveState, StateNotificationPostProcessState, WDF_STATE_NOTIFICATION_TYPE, WDF_STATE_NOTIFICATION_TYPE enumeration, _WDF_STATE_NOTIFICATION_TYPE, kmdf.wdf_state_notification_type, wdf.wdf_state_notification_type, wdfdevice/StateNotificationAllStates, wdfdevice/StateNotificationEnterState, wdfdevice/StateNotificationInvalid, wdfdevice/StateNotificationLeaveState, wdfdevice/StateNotificationPostProcessState, wdfdevice/WDF_STATE_NOTIFICATION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_STATE_NOTIFICATION_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# _WDF_STATE_NOTIFICATION_TYPE Enumeration
<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_STATE_NOTIFICATION_TYPE</b> enumeration identifies the type of Plug and Play, power, or power policy notification that a framework-based driver will receive.

## Syntax
```
typedef enum _WDF_STATE_NOTIFICATION_TYPE {
  StateNotificationInvalid           ,
  StateNotificationEnterState        ,
  StateNotificationPostProcessState  ,
  StateNotificationLeaveState        ,
  StateNotificationAllStates
} WDF_STATE_NOTIFICATION_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>StateNotificationInvalid</td>
                    <td>For internal use only.</td>
                </tr>
            
                <tr>
                    <td>StateNotificationEnterState</td>
                    <td>The driver is notified immediately before a device's Plug and Play, power, or power policy state machine enters a specified state.</td>
                </tr>
            
                <tr>
                    <td>StateNotificationPostProcessState</td>
                    <td>The driver is notified immediately after a device's Plug and Play, power, or power policy state machine enters a specified state.</td>
                </tr>
            
                <tr>
                    <td>StateNotificationLeaveState</td>
                    <td>The driver is notified immediately before a device's Plug and Play, power, or power policy state machine leaves a specified state.</td>
                </tr>
            
                <tr>
                    <td>StateNotificationAllStates</td>
                    <td>The driver receives enter-state, postprocess-state, and leave-state notifications.</td>
                </tr>
</table>

## Remarks

When the framework's state machine for a driver's device changes from state <i>a</i> to state <i>b</i>, the framework notifies the driver (if the driver registered an appropriate event callback function), in the following sequence:

<ol>
<li>
Calls state <i>a</i>'s leave-state notification callback function.

</li>
<li>
Calls state <i>b</i>'s enter-state notification callback function.

</li>
<li>
Changes the device's state from <i>a</i> to <i>b</i>.

</li>
<li>
Calls state <i>b</i>'s postprocess-state notification callback function.

</li>
</ol>
To register for notification of a change in state, the driver can call the following methods:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546057">WdfDeviceInitRegisterPnpStateChangeCallback</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546071">WdfDeviceInitRegisterPowerStateChangeCallback</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546066">WdfDeviceInitRegisterPowerPolicyStateChangeCallback</a>


</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551260">WDF_DEVICE_PNP_NOTIFICATION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551268">WDF_DEVICE_POWER_NOTIFICATION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551273">WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA</a>