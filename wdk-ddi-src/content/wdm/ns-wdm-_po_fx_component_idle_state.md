---
UID : NS:wdm._PO_FX_COMPONENT_IDLE_STATE
title : "_PO_FX_COMPONENT_IDLE_STATE"
author : windows-driver-content
description : The PO_FX_COMPONENT_IDLE_STATE structure specifies the attributes of an Fx power state of a component in a device.
old-location : kernel\po_fx_component_idle_state.htm
old-project : kernel
ms.assetid : 4F0BF45D-F854-480C-B0AC-8134C6BF3266
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PPO_FX_COMPONENT_IDLE_STATE, wdm/PPO_FX_COMPONENT_IDLE_STATE, *PPO_FX_COMPONENT_IDLE_STATE, PPO_FX_COMPONENT_IDLE_STATE structure pointer [Kernel-Mode Driver Architecture], _PO_FX_COMPONENT_IDLE_STATE, PO_FX_COMPONENT_IDLE_STATE, wdm/PO_FX_COMPONENT_IDLE_STATE, PO_FX_COMPONENT_IDLE_STATE structure [Kernel-Mode Driver Architecture], kernel.po_fx_component_idle_state
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wdm.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 8.
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
req.irql : PASSIVE_LEVEL (see Remarks section)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPO_FX_COMPONENT_IDLE_STATE, PO_FX_COMPONENT_IDLE_STATE"
req.product : Windows 10 or later.
---

# _PO_FX_COMPONENT_IDLE_STATE structure
The <b>PO_FX_COMPONENT_IDLE_STATE</b> structure specifies the attributes of an Fx power state of a component in a device.

## Syntax
````
typedef struct _PO_FX_COMPONENT_IDLE_STATE {
  ULONGLONG TransitionLatency;
  ULONGLONG ResidencyRequirement;
  ULONG     NominalPower;
} PO_FX_COMPONENT_IDLE_STATE, *PPO_FX_COMPONENT_IDLE_STATE;
````

## Members


`NominalPower`

The power, in microwatts, that the component consumes in this Fx state. Set this member to <b>PO_FX_UNKNOWN_POWER</b> to indicate that PoFx should ignore (treat as negligible) the component's internal power consumption in this Fx state when PoFx evaluates which power state to switch to when the component is idle.

`ResidencyRequirement`

The residency requirement. The residency requirement is the minimum amount of time, in 100-nanosecond units, that the component must spend in this Fx state to make a transition to this Fx state worthwhile. PoFx uses this member value as a hint to avoid switching a component to an Fx state unless the component is likely to remain in this state for at least the amount of time specified by <b>ResidencyRequirement</b>. For a <b>PO_FX_COMPONENT_IDLE_STATE</b> structure that describes the attributes of the F0 state, set this member to zero.

`TransitionLatency`

The transition latency. This latency is the amount of time, in 100-nanosecond units, that the component requires to return from this Fx state to the F0 state. For a <b>PO_FX_COMPONENT_IDLE_STATE</b> structure that specifies the attributes of the F0 state, set this member to zero.

## Remarks
The <a href="..\wdm\ns-wdm-_po_fx_component_v2.md">PO_FX_COMPONENT</a> structure contains a pointer to an array of <b>PO_FX_COMPONENT_IDLE_STATE</b> structures. Each array element specifies the attributes of an Fx state. Element 0 describes F0, element 1 describes F1, and so on.

When the driver registers a device with PoFx, the driver supplies an array of <b>PO_FX_COMPONENT</b> structures. Each array element describes the power attributes of a component in the device.

Do not set <b>TransitionLatency</b> and <b>ResidencyRequirement</b> to <b>PO_FX_UNKNOWN_TIME</b> because  it may prevent the power management framework (PoFx) from selecting the idle state.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | wdm.h |

## See Also

<a href="..\wdm\ns-wdm-_po_fx_component_v2.md">PO_FX_COMPONENT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_COMPONENT_IDLE_STATE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>