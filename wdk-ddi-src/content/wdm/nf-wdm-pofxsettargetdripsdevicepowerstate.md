---
UID : NF:wdm.PoFxSetTargetDripsDevicePowerState
title : PoFxSetTargetDripsDevicePowerState function
author : windows-driver-content
description : This routine is called to notify the power manager of the device's target device power state for DRIPS. The driver can override the DRIPS constraint provided by the PEP.
old-location : kernel\pofxsettargetdripsdevicepowerstate.htm
old-project : kernel
ms.assetid : 435c0731-101c-498b-9041-904001be3f2c
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PoFxSetTargetDripsDevicePowerState function [Kernel-Mode Driver Architecture], PoFxSetTargetDripsDevicePowerState, wdm/PoFxSetTargetDripsDevicePowerState, kernel.pofxsettargetdripsdevicepowerstate
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1709
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe (kernel mode)
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# PoFxSetTargetDripsDevicePowerState function
This routine is called to notify the power manager of the device's target
    device power state for DRIPS.  The driver can override the
    DRIPS constraint provided by the PEP.

## Syntax

````
NTSTATUS  PoFxSetTargetDripsDevicePowerState(
  _In_ POHANDLE           Handle,
  _In_ DEVICE_POWER_STATE TargetState
);
````

## Parameters

`Handle`

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> routine.

`TargetState`

Specifies the target DRIPS device power state. Possible values are defined in the <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a> enumeration. This value must
    be lower than the existing device constraint.  A device power state
    of <b>PowerDeviceUnspecified</b> resets to the PEP provided constraint.


## Return Value

Returns STATUS_SUCCESS if the target state was accepted.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |