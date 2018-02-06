---
UID: NS:d3dkmddi._DXGK_POWER_RUNTIME_STATE
title: "_DXGK_POWER_RUNTIME_STATE"
author: windows-driver-content
description: Describes the characteristics of an idle state (an F-state).
old-location: display\dxgk_power_runtime_state.htm
old-project: display
ms.assetid: f2bfb07c-1493-4a29-9d42-e284af29a376
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_DXGK_POWER_RUNTIME_STATE, DXGK_POWER_RUNTIME_STATE structure [Display Devices], DXGK_POWER_RUNTIME_STATE, d3dkmddi/DXGK_POWER_RUNTIME_STATE, display.dxgk_power_runtime_state"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dkmddi.h
apiname:
-	DXGK_POWER_RUNTIME_STATE
product: Windows
targetos: Windows
req.typenames: DXGK_POWER_RUNTIME_STATE
---

# _DXGK_POWER_RUNTIME_STATE structure
Describes the characteristics of an idle state (an F-state).

## Syntax
````
typedef struct _DXGK_POWER_RUNTIME_STATE {
  ULONGLONG TransitionLatency;
  ULONGLONG ResidencyRequirement;
  ULONGLONG NominalPower;
} DXGK_POWER_RUNTIME_STATE;
````

## Members


`NominalPower`

The power draw, in microwatt units, of the component in this F-state. This  value should not be zero for the F0 state.

`ResidencyRequirement`

The minimal amount of time, in 100-nanosecond units, that is required to spend in
   this F-state to make it worthwhile. This value should be zero for the F0 state.

`TransitionLatency`

The amount of time, in 100-nanosecond units, that the component takes to return to the F0 state.
   This value should be zero for the F0 state.

## Remarks
F-states in hardware must be defined such that a deeper F-state (higher F-value) will use less power and take longer to return to the latent F0 state.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmddi.h |