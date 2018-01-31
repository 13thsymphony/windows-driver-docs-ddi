---
UID : NE:pepfx._PEP_PERF_STATE_UNIT
title : "_PEP_PERF_STATE_UNIT"
author : windows-driver-content
description : The PEP_PERF_STATE_UNIT enumeration indicates the measurement units in which the performance state (P-state) of a component is specified.
old-location : kernel\pep_perf_state_unit.htm
old-project : kernel
ms.assetid : 5E5F049D-4306-4382-B3F7-06C1F5FFE93E
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.pep_perf_state_unit, PepPerfStateUnitOther, *PPEP_PERF_STATE_UNIT, PEP_PERF_STATE_UNIT, _PEP_PERF_STATE_UNIT, pepfx/PepPerfStateUnitOther, pepfx/PepPerfStateUnitFrequency, PepPerfStateUnitFrequency, PepPerfStateUnitMax, pepfx/PEP_PERF_STATE_UNIT, pepfx/PepPerfStateUnitMax, PEP_PERF_STATE_UNIT enumeration [Kernel-Mode Driver Architecture], PepPerfStateUnitBandwidth, pepfx/PepPerfStateUnitBandwidth
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPEP_PERF_STATE_UNIT, PEP_PERF_STATE_UNIT"
---

# _PEP_PERF_STATE_UNIT Enumeration
The <b>PEP_PERF_STATE_UNIT</b> enumeration indicates the measurement units in which the performance state (P-state) of a component is specified.

## Syntax
````
typedef enum _PEP_PERF_STATE_UNIT { 
  PepPerfStateUnitOther      = 0,
  PepPerfStateUnitFrequency,
  PepPerfStateUnitBandwidth,
  PepPerfStateUnitMax
} PEP_PERF_STATE_UNIT;
````

## Constants

<table>

<tr>
<td>PepPerfStateUnitBandwidth</td>
<td>Bits per second (bandwidth units).</td>
</tr>

<tr>
<td>PepPerfStateUnitFrequency</td>
<td>Hertz (frequency units).</td>
</tr>

<tr>
<td>PepPerfStateUnitMax</td>
<td>Reserved for use by operating system.</td>
</tr>

<tr>
<td>PepPerfStateUnitOther</td>
<td>Some other type of measurement units not explicitly described by this enumeration.</td>
</tr>
</table>

## Remarks

The <b>Type</b> member of the <a href="..\pepfx\ns-pepfx-_pep_component_perf_set.md">PEP_COMPONENT_PERF_SET</a> structure is a <b>PEP_PERF_STATE_UNIT</b> enumeration value.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_component_perf_set.md">PEP_COMPONENT_PERF_SET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PERF_STATE_UNIT enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>