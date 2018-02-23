---
UID: NS:wdm._PO_FX_COMPONENT_PERF_SET
title: "_PO_FX_COMPONENT_PERF_SET"
author: windows-driver-content
description: The PO_FX_COMPONENT_PERF_SET structure represents a set of performance states for a single component within a device.
old-location: kernel\po_fx_component_perf_set.htm
old-project: kernel
ms.assetid: 2305BE73-8363-4534-A64D-06C91F636E2F
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "_PO_FX_COMPONENT_PERF_SET, PPO_FX_COMPONENT_PERF_SET, PO_FX_COMPONENT_PERF_SET structure [Kernel-Mode Driver Architecture], PPO_FX_COMPONENT_PERF_SET structure pointer [Kernel-Mode Driver Architecture], wdm/PO_FX_COMPONENT_PERF_SET, wdm/PPO_FX_COMPONENT_PERF_SET, PO_FX_COMPONENT_PERF_SET, *PPO_FX_COMPONENT_PERF_SET, kernel.po_fx_component_perf_set"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	PO_FX_COMPONENT_PERF_SET
product: Windows
targetos: Windows
req.typenames: PO_FX_COMPONENT_PERF_SET, *PPO_FX_COMPONENT_PERF_SET
req.product: Windows 10 or later.
---

# _PO_FX_COMPONENT_PERF_SET structure
The <b>PO_FX_COMPONENT_PERF_SET</b> structure represents a set of performance states for a single component within a device.

## Syntax
````
typedef struct _PO_FX_COMPONENT_PERF_SET {
  UNICODE_STRING        Name;
  ULONGLONG             Flags;
  PO_FX_PERF_STATE_UNIT Unit;
  PO_FX_PERF_STATE_TYPE Type;
  union {
    struct {
      ULONG             Count;
      PPO_FX_PERF_STATE States;
    } Discrete;
    struct {
      ULONGLONG Minimum;
      ULONGLONG Maximum;
    } Range;
  };
} PO_FX_COMPONENT_PERF_SET, *PPO_FX_COMPONENT_PERF_SET;
````

## Members


`Flags`

Set to 0. Currently, no flags are defined for this member.

`Name`

An optional character string used to describe the component property controlled by the performance state set. For example, "Clock frequency" or "Memory bandwidth".

`Type`

A <a href="..\wudfwdm\ne-wudfwdm-_po_fx_perf_state_type.md">PO_FX_PERF_STATE_TYPE</a> value that specifies the type of performance states in the set (a discrete number of states or a continuous distribution of states between a minimum and maximum value).

`Unit`

A <a href="..\wudfwdm\ne-wudfwdm-_po_fx_perf_state_unit.md">PO_FX_PERF_STATE_UNIT</a> value that specifies the type of unit that is controlled by the performance state set.

## Remarks
When a device driver calls the <a href="..\wdm\nf-wdm-pofxregistercomponentperfstates.md">PoFxRegisterComponentPerfStates</a> routine to register a component for performance state support with the power management framework (PoFx),  the driver can supply a <a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_perf_info.md">PO_FX_COMPONENT_PERF_INFO</a> structure that  describes the sets of the performance states supported by the component. The <b>PerfStateSets</b> member of the <b>PO_FX_COMPONENT_PERF_INFO</b> structure contains an array of <b>PO_FX_COMPONENT_PERF_SET</b> structures that represent the supported performance states.

Most drivers are expected to define a single set of performance states per component. For example, a driver might define one set of performance states to control the clock frequency for a component. However, some drivers may need to define more than one performance state set to control multiple dimensions of performance states for a component. For example, a driver might define two sets of performance states to control the clock frequency and bus bandwidth.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | wdm.h (include Wudfwdm.h) |

## See Also

<a href="https://msdn.microsoft.com/D5341D6D-7C71-43CB-9C70-7E939B32C33F">Device Performance State Management</a>



<a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_perf_info.md">PO_FX_COMPONENT_PERF_INFO</a>



<a href="..\wdm\nf-wdm-pofxregistercomponentperfstates.md">PoFxRegisterComponentPerfStates</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_COMPONENT_PERF_SET structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>