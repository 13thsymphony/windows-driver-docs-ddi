---
UID: NE:pepfx._PEP_PERF_STATE_TYPE
title: "_PEP_PERF_STATE_TYPE"
author: windows-driver-content
description: The PEP_PERF_STATE_TYPE enumeration indicates the type of performance information that is specified for a performance state (P-state) of a component.
old-location: kernel\pep_perf_state_type.htm
old-project: kernel
ms.assetid: 8DF40988-995E-4C37-8864-0C405DE885C9
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_PERF_STATE_TYPE, PEP_PERF_STATE_TYPE, PEP_PERF_STATE_TYPE enumeration [Kernel-Mode Driver Architecture], PepPerfStateTypeDiscrete, PepPerfStateTypeMax, PepPerfStateTypeRange, _PEP_PERF_STATE_TYPE, kernel.pep_perf_state_type, pepfx/PEP_PERF_STATE_TYPE, pepfx/PepPerfStateTypeDiscrete, pepfx/PepPerfStateTypeMax, pepfx/PepPerfStateTypeRange"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pepfx.h
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
req.irql: See Remarks.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PERF_STATE_TYPE
product: Windows
targetos: Windows
req.typenames: PEP_PERF_STATE_TYPE, *PPEP_PERF_STATE_TYPE
---

# _PEP_PERF_STATE_TYPE Enumeration
The <b>PEP_PERF_STATE_TYPE</b> enumeration indicates the type of performance information that is specified for a performance state (P-state) of a component.

## Syntax
````
typedef enum _PEP_PERF_STATE_TYPE { 
  PepPerfStateTypeDiscrete  = 0,
  PepPerfStateTypeRange,
  PepPerfStateTypeMax
} PEP_PERF_STATE_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>PepPerfStateTypeDiscrete</td>
                    <td>The performance information is specified as a set of discrete values.</td>
                </tr>
            
                <tr>
                    <td>PepPerfStateTypeRange</td>
                    <td>The performance information is specified as a range of values.</td>
                </tr>
            
                <tr>
                    <td>PepPerfStateTypeMax</td>
                    <td>Reserved for use by operating system.</td>
                </tr>
</table>

## Remarks

The <b>Type</b> member of the <a href="..\pepfx\ns-pepfx-_pep_component_perf_set.md">PEP_COMPONENT_PERF_SET</a> structure is a <b>PEP_PERF_STATE_TYPE</b> enumeration value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_component_perf_set.md">PEP_COMPONENT_PERF_SET</a>