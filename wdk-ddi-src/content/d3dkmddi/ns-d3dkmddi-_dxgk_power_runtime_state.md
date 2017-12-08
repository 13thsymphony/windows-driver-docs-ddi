---
UID: NS.D3DKMDDI._DXGK_POWER_RUNTIME_STATE
title: _DXGK_POWER_RUNTIME_STATE
author: windows-driver-content
description: Describes the characteristics of an idle state (an F-state).
old-location: display\dxgk_power_runtime_state.htm
old-project: display
ms.assetid: f2bfb07c-1493-4a29-9d42-e284af29a376
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_POWER_RUNTIME_STATE, DXGK_POWER_RUNTIME_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_POWER_RUNTIME_STATE
req.alt-loc: D3dkmddi.h
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
---

# _DXGK_POWER_RUNTIME_STATE structure



## -description
Describes the characteristics of an idle state (an F-state).


## -syntax

````
typedef struct _DXGK_POWER_RUNTIME_STATE {
  ULONGLONG TransitionLatency;
  ULONGLONG ResidencyRequirement;
  ULONGLONG NominalPower;
} DXGK_POWER_RUNTIME_STATE;
````


## -struct-fields

### -field TransitionLatency

The amount of time, in 100-nanosecond units, that the component takes to return to the F0 state.
   This value should be zero for the F0 state.

### -field ResidencyRequirement

The minimal amount of time, in 100-nanosecond units, that is required to spend in
   this F-state to make it worthwhile. This value should be zero for the F0 state.

### -field NominalPower

The power draw, in microwatt units, of the component in this F-state. This  value should not be zero for the F0 state.

## -remarks
F-states in hardware must be defined such that a deeper F-state (higher F-value) will use less power and take longer to return to the latent F0 state.

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>