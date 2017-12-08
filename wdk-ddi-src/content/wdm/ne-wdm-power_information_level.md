---
UID: NE.wdm.POWER_INFORMATION_LEVEL
title: POWER_INFORMATION_LEVEL
author: windows-driver-content
description: Indicates power level information.
old-location: kernel\power_information_level.htm
old-project: kernel
ms.assetid: DCAB0482-C0E3-4F75-B5A7-FB8DFFA89D6F
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: POWER_INFORMATION_LEVEL, POWER_INFORMATION_LEVEL
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
req.alt-api: POWER_INFORMATION_LEVEL
req.alt-loc: wdm.h
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
req.product: Windows 10 or later.
---

# POWER_INFORMATION_LEVEL enumeration



## -description
Indicates power level information.


## -syntax

````
typedef enum _POWER_INFORMATION_LEVEL { 
  SystemPowerPolicyAc,
  SystemPowerPolicyDc,
  VerifySystemPolicyAc,
  VerifySystemPolicyDc,
  SystemPowerCapabilities,
  SystemBatteryState,
  SystemPowerStateHandler,
  ProcessorStateHandler,
  SystemPowerPolicyCurrent,
  AdministratorPowerPolicy,
  SystemReserveHiberFile,
  ProcessorInformation,
  SystemPowerInformation,
  ProcessorStateHandler2,
  LastWakeTime,
  LastSleepTime,
  SystemExecutionState,
  SystemPowerStateNotifyHandler,
  ProcessorPowerPolicyAc,
  ProcessorPowerPolicyDc,
  VerifyProcessorPowerPolicyAc,
  VerifyProcessorPowerPolicyDc,
  ProcessorPowerPolicyCurrent,
  SystemPowerStateLogging,
  SystemPowerLoggingEntry,
  SetPowerSettingValue,
  NotifyUserPowerSetting,
  PowerInformationLevelUnused0,
  SystemMonitorHiberBootPowerOff,
  SystemVideoState,
  TraceApplicationPowerMessage,
  TraceApplicationPowerMessageEnd,
  ProcessorPerfStates,
  ProcessorIdleStates,
  ProcessorCap,
  SystemWakeSource,
  SystemHiberFileInformation,
  TraceServicePowerMessage,
  ProcessorLoad,
  PowerShutdownNotification,
  MonitorCapabilities,
  SessionPowerInit,
  SessionDisplayState,
  PowerRequestCreate,
  PowerRequestAction,
  GetPowerRequestList,
  ProcessorInformationEx,
  NotifyUserModeLegacyPowerEvent,
  GroupPark,
  ProcessorIdleDomains,
  WakeTimerList,
  SystemHiberFileSize,
  ProcessorIdleStatesHv,
  ProcessorPerfStatesHv,
  ProcessorPerfCapHv,
  ProcessorSetIdle,
  LogicalProcessorIdling,
  UserPresence,
  PowerSettingNotificationName,
  GetPowerSettingValue,
  IdleResiliency,
  SessionRITState,
  SessionConnectNotification,
  SessionPowerCleanup,
  SessionLockState,
  SystemHiberbootState,
  PlatformInformation,
  PdcInvocation,
  MonitorInvocation,
  FirmwareTableInformationRegistered,
  SetShutdownSelectedTime,
  SuspendResumeInvocation,
  PlmPowerRequestCreate,
  ScreenOff,
  CsDeviceNotification,
  PlatformRole,
  LastResumePerformance,
  DisplayBurst,
  ExitLatencySamplingPercentage,
  RegisterSpmPowerSettings,
  PlatformIdleStates,
  ProcessorIdleVeto,
  PlatformIdleVeto,
  SystemBatteryStatePrecise,
  ThermalEvent,
  PowerRequestActionInternal,
  BatteryDeviceState,
  PowerInformationInternal,
  ThermalStandby,
  SystemHiberFileType,
  PhysicalPowerButtonPress,
  QueryPotentialDripsConstraint,
  EnergyTrackerCreate,
  EnergyTrackerQuery,
  UpdateBlackBoxRecorder,
  PowerInformationLevelMaximum
} POWER_INFORMATION_LEVEL;
````


## -enum-fields

### -field SystemPowerPolicyAc

Indicates SystemPowerPolicyAc.

### -field SystemPowerPolicyDc

Indicates SystemPowerPolicyDc.

### -field VerifySystemPolicyAc

Indicates VerifySystemPolicyAc.

### -field VerifySystemPolicyDc

Indicates VerifySystemPolicyDc.

### -field SystemPowerCapabilities

Indicates the power capabilities of the system.

### -field SystemBatteryState

Indicates the system's battery state.

### -field SystemPowerStateHandler

Indicates the system's power state handler.

### -field ProcessorStateHandler

Indicates the processor state handler.

### -field SystemPowerPolicyCurrent

Indicates the system's current power policy.

### -field AdministratorPowerPolicy

Indicates the administrator's power policy.

### -field SystemReserveHiberFile

Indicates the SystemReserveHiberFile.

### -field ProcessorInformation

Indicates the processor information.

### -field SystemPowerInformation

Indicates the system power information.

### -field ProcessorStateHandler2

Indicates the processor state handler.

### -field LastWakeTime

Indicates the last wake time.

### -field LastSleepTime

Indicates the last sleep time.

### -field SystemExecutionState

Indicates the system execution state.

### -field SystemPowerStateNotifyHandler

Indicates the system power state notify handler.

### -field ProcessorPowerPolicyAc

Indicates ProcessorPowerPolicyAc.

### -field ProcessorPowerPolicyDc

Indicates ProcessorPowerPolicyDc.

### -field VerifyProcessorPowerPolicyAc

Indicates VerifyProcessorPowerPolicyAc.

### -field VerifyProcessorPowerPolicyDc

Indicates VerifyProcessorPowerPolicyDc.

### -field ProcessorPowerPolicyCurrent

Indicates the current processor power policy.

### -field SystemPowerStateLogging

Indicates SystemPowerStateLogging.

### -field SystemPowerLoggingEntry

Indicates SystemPowerLoggingEntry.

### -field SetPowerSettingValue

Indicates that the power setting value is set.

### -field NotifyUserPowerSetting

Indicates that the user should be notified of the power setting.

### -field PowerInformationLevelUnused0

Indicates that the power information level is unused.

### -field SystemMonitorHiberBootPowerOff

Indicates that the system monitor boot power is off.

### -field SystemVideoState

Indicates the system video state.

### -field TraceApplicationPowerMessage

Indicates the trace application power message.

### -field TraceApplicationPowerMessageEnd

Indicates the end of the trace application power message.

### -field ProcessorPerfStates

Indicates the processor performance states.

### -field ProcessorIdleStates

Indicates the processor idle states.

### -field ProcessorCap

Indicates the processor cap.

### -field SystemWakeSource

Indicates the system wake source.

### -field SystemHiberFileInformation

Indicates the system's hibernation file information.

### -field TraceServicePowerMessage

Indicates the trace service power message.

### -field ProcessorLoad

Indicates the processor load.

### -field PowerShutdownNotification

Indicates the power shutdown notification.

### -field MonitorCapabilities

Indicates the monitor's capabilities.

### -field SessionPowerInit

Indicates the session power has been initialized.

### -field SessionDisplayState

Indicates the session display state.

### -field PowerRequestCreate

Indicates that a power request has been created.

### -field PowerRequestAction

Indicates the action of the power request.

### -field GetPowerRequestList

Indicates that the power request list should be queued. 

### -field ProcessorInformationEx

Indicates ProcessorInformationEx.

### -field NotifyUserModeLegacyPowerEvent

Indicates that a notification should be created for the user mode legacy power event.

### -field GroupPark

Indicates the group park.

### -field ProcessorIdleDomains

Indicates the processor's idle domains.

### -field WakeTimerList

Indicates the wake timer list.

### -field SystemHiberFileSize

Indicates the system's hibernation file size.

### -field ProcessorIdleStatesHv

Indicates the processor's idle states.

### -field ProcessorPerfStatesHv

Indicates the processor's performance states.

### -field ProcessorPerfCapHv

Indicates the processor's performance capabilities.

### -field ProcessorSetIdle

Indicates that the processor has been set to idle.

### -field LogicalProcessorIdling

Indicates that the processor is idling.

### -field UserPresence

Indicates the user presence.

### -field PowerSettingNotificationName

Indicates the power setting notification name.

### -field GetPowerSettingValue

Indicates that the power setting value should be queued.

### -field IdleResiliency

Indicates the idle resiliency.

### -field SessionRITState

Indicates the session's RIT state.

### -field SessionConnectNotification

Indicates the session's connect notification.

### -field SessionPowerCleanup

Indicates the session's power cleanup.

### -field SessionLockState

Indicates the session's lock state.

### -field SystemHiberbootState

Indicates the system's hibernation boot state.

### -field PlatformInformation

Indicates the platform information.

### -field PdcInvocation

Indicates the pdc invocation.

### -field MonitorInvocation

Indicates the monitor invocation.

### -field FirmwareTableInformationRegistered

Indicates the registered firmware table information.

### -field SetShutdownSelectedTime

Indicates that the shutdown time should be set.

### -field SuspendResumeInvocation

Indicates SuspendResumeInvocation.

### -field PlmPowerRequestCreate

Indicates that the power request has been created.

### -field ScreenOff

Indicates that the screen is off.

### -field CsDeviceNotification

Indicates the device notification.

### -field PlatformRole

Indicates the platform role.

### -field LastResumePerformance

Indicates the last time performance was resumed.

### -field DisplayBurst

Indicates display burst.

### -field ExitLatencySamplingPercentage

Indicates the latency sampling percentage.

### -field RegisterSpmPowerSettings

Indicates that the power settings are registered.

### -field PlatformIdleStates

Indicates the platform's idle states.

### -field ProcessorIdleVeto

Indicates the processor's idle veto.

### -field PlatformIdleVeto

Indicates the platform's idle veto.

### -field SystemBatteryStatePrecise

Indicates the system's battery state.

### -field ThermalEvent

Indicates the thermal event.

### -field PowerRequestActionInternal

Indicates the internal power request action.

### -field BatteryDeviceState

Indicates the battery's device state.	

### -field PowerInformationInternal

Indicates the internal power information.

### -field ThermalStandby

Indicates thermal standby.

### -field SystemHiberFileType

Indicates the system's hibernation file type.

### -field PhysicalPowerButtonPress

Indicates a physical power button press.

### -field QueryPotentialDripsConstraint

Indicates the potential drips constraint.

### -field EnergyTrackerCreate

Indicates that the energy tracker is created.

### -field EnergyTrackerQuery

Indicates that the energy tracker is queried.

### -field UpdateBlackBoxRecorder

Indicates that the black box recorder is updated.

### -field PowerInformationLevelMaximum

Indicates the maximum power level.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
</table>