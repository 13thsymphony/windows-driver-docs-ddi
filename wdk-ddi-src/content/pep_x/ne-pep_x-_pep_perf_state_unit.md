---
UID: NE:pep_x._PEP_PERF_STATE_UNIT
title: "_PEP_PERF_STATE_UNIT"
author: windows-driver-content
description: The PEP_PERF_STATE_UNIT enumeration indicates the measurement units in which the performance state (P-state) of a component is specified.
old-location: kernel\pep_perf_state_unit.htm
old-project: kernel
ms.assetid: 5E5F049D-4306-4382-B3F7-06C1F5FFE93E
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_PERF_STATE_UNIT, PEP_PERF_STATE_UNIT, PEP_PERF_STATE_UNIT enumeration [Kernel-Mode Driver Architecture], PepPerfStateUnitBandwidth, PepPerfStateUnitFrequency, PepPerfStateUnitMax, PepPerfStateUnitOther, _PEP_PERF_STATE_UNIT, kernel.pep_perf_state_unit, pepfx/PEP_PERF_STATE_UNIT, pepfx/PepPerfStateUnitBandwidth, pepfx/PepPerfStateUnitFrequency, pepfx/PepPerfStateUnitMax, pepfx/PepPerfStateUnitOther"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pep_x.h
req.include-header: Pep_x.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PERF_STATE_UNIT
product:
- Windows
targetos: Windows
req.typenames: PEP_PERF_STATE_UNIT, *PPEP_PERF_STATE_UNIT, PEP_PERF_STATE_UNIT, *PPEP_PERF_STATE_UNIT
---

# _PEP_PERF_STATE_UNIT Enumeration
The <b>PEP_PERF_STATE_UNIT</b> enumeration indicates the measurement units in which the performance state (P-state) of a component is specified.

## Syntax
```
typedef enum _PEP_PERF_STATE_UNIT {
  PepPerfStateUnitOther      ,
  PepPerfStateUnitFrequency  ,
  PepPerfStateUnitBandwidth  ,
  PepPerfStateUnitMax
} PEP_PERF_STATE_UNIT, *PPEP_PERF_STATE_UNIT;
```

## Constants

<table>
            
                <tr>
                    <td>PepPerfStateUnitOther</td>
                    <td>Some other type of measurement units not explicitly described by this enumeration.</td>
                </tr>
            
                <tr>
                    <td>PepPerfStateUnitFrequency</td>
                    <td>Hertz (frequency units).</td>
                </tr>
            
                <tr>
                    <td>PepPerfStateUnitBandwidth</td>
                    <td>Bits per second (bandwidth units).</td>
                </tr>
            
                <tr>
                    <td>PepPerfStateUnitMax</td>
                    <td>Reserved for use by operating system.</td>
                </tr>
</table>

## Remarks

The <b>Type</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186702">PEP_COMPONENT_PERF_SET</a> structure is a <b>PEP_PERF_STATE_UNIT</b> enumeration value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt186702">PEP_COMPONENT_PERF_SET</a>