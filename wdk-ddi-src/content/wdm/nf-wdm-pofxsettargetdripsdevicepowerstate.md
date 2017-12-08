---
UID: NF.wdm.PoFxSetTargetDripsDevicePowerState
title: PoFxSetTargetDripsDevicePowerState function
author: windows-driver-content
description: This routine is called to notify the power manager of the device's target device power state for DRIPS. The driver can override the DRIPS constraint provided by the PEP.
old-location: kernel\pofxsettargetdripsdevicepowerstate.htm
old-project: kernel
ms.assetid: 435c0731-101c-498b-9041-904001be3f2c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PoFxSetTargetDripsDevicePowerState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PoFxSetTargetDripsDevicePowerState
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# PoFxSetTargetDripsDevicePowerState function



## -description
    This routine is called to notify the power manager of the device's target
    device power state for DRIPS.  The driver can override the
    DRIPS constraint provided by the PEP.  


## -syntax

````
NTSTATUS  PoFxSetTargetDripsDevicePowerState(
  _In_ POHANDLE           Handle,
  _In_ DEVICE_POWER_STATE TargetState
);
````


## -parameters

### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="kernel.pofxregisterdevice">PoFxRegisterDevice</a> routine.

### -param TargetState [in]

Specifies the target DRIPS device power state. Possible values are defined in the <a href="kernel.device_power_state">DEVICE_POWER_STATE</a> enumeration. This value must
    be lower than the existing device constraint.  A device power state
    of <b>PowerDeviceUnspecified</b> resets to the PEP provided constraint.

## -returns
Returns STATUS_SUCCESS if the target state was accepted.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10, version 1709
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
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
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe (kernel mode)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>