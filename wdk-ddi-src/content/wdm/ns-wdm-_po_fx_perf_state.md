---
UID: NS:wdm._PO_FX_PERF_STATE
title: "_PO_FX_PERF_STATE"
author: windows-driver-content
description: The PO_FX_PERF_STATE structure represents a performance state for a single component within a device.
old-location: kernel\po_fx_perf_state.htm
old-project: kernel
ms.assetid: 06A41593-A052-43A7-B3A7-02185B557FA3
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPO_FX_PERF_STATE, PO_FX_PERF_STATE, PO_FX_PERF_STATE structure [Kernel-Mode Driver Architecture], PPO_FX_PERF_STATE, PPO_FX_PERF_STATE structure pointer [Kernel-Mode Driver Architecture], _PO_FX_PERF_STATE, kernel.po_fx_perf_state, wdm/PO_FX_PERF_STATE, wdm/PPO_FX_PERF_STATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wudfwdm.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	PO_FX_PERF_STATE
product: Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE, *PPO_FX_PERF_STATE
req.product: Windows 10 or later.
---

# _PO_FX_PERF_STATE structure
The <b>PO_FX_PERF_STATE</b> structure represents a performance state for a single component within a device.

## Syntax
```
typedef struct _PO_FX_PERF_STATE {
  ULONGLONG Value;
  PVOID     Context;
} *PPO_FX_PERF_STATE, PO_FX_PERF_STATE;
```

## Members


`Value`

The value of this performance state. The units are specified by the <b>Unit</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> that contains this performance state. For example, if <b>Value</b> is 100000000 and the <b>Unit</b> member of the  <b>PO_FX_COMPONENT_PERF_SET</b> is <b>PoFxPerfStateUnitFrequency</b>, this performance state represents 100 MHz.

`Context`

A pointer to additional context for the performance state that cannot be presented by the <b>Value</b> member. This data can be shared between the driver and the platform extension plug-in (PEP).

<div class="alert"><b>Note</b>  Using the <b>Context</b> member can hinder the visualization of performance states in Windows Performance Analyzer.</div>
<div> </div>

## Remarks
The <b>States</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a> structure contains an array of <b>PO_FX_PERF_STATE</b> elements.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | wdm.h (include Wudfwdm.h) |

## See Also

<a href="https://msdn.microsoft.com/D5341D6D-7C71-43CB-9C70-7E939B32C33F">Device Performance State Management</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939833">PO_FX_COMPONENT_PERF_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939838">PO_FX_PERF_STATE_UNIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn939778">PoFxRegisterComponentPerfStates</a>