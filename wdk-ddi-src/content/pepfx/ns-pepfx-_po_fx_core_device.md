---
UID: NS.PEPFX._PO_FX_CORE_DEVICE
title: _PO_FX_CORE_DEVICE
author: windows-driver-content
description: The PO_FX_CORE_DEVICE structure contains information about the power-state attributes of the components in a core system resource, and provides a software interface for power-managing these components.
old-location: kernel\po_fx_core_device.htm
old-project: kernel
ms.assetid: 46C16795-412B-48E7-A7E8-E474CEC51849
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _PO_FX_CORE_DEVICE, *PPO_FX_CORE_DEVICE, PO_FX_CORE_DEVICE, PPO_FX_CORE_DEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PO_FX_CORE_DEVICE
req.alt-loc: pepfx.h
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

# _PO_FX_CORE_DEVICE structure



## -description
The <b>PO_FX_CORE_DEVICE</b> structure contains information about the power-state attributes of the components in a core system resource, and provides a software interface for power-managing these components.



## -syntax

````
typedef struct _PO_FX_CORE_DEVICE {
  ULONG                                         Version;
  ULONG                                         ComponentCount;
  PPO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK    ComponentActiveConditionCallback;
  PPO_FX_COMPONENT_IDLE_CONDITION_CALLBACK      ComponentIdleConditionCallback;
  PPO_FX_COMPONENT_CRITICAL_TRANSITION_CALLBACK ComponentCriticalTransitionCallback;
  PPO_FX_COMPONENT_IDLE_STATE_CALLBACK          ComponentIdleStateCallback;
  PVOID                                         DeviceContext;
  PO_FX_COMPONENT                               Components[ANYSIZE_ARRAY];
} PO_FX_CORE_DEVICE, *PPO_FX_CORE_DEVICE;
````


## -struct-fields

### -field Version

The version number of this structure.


### -field ComponentCount

The number of elements in the <b>Components</b> array at the end of this structure. This count includes all elements of the array, and includes both the first element, which is a member of this structure,  and any additional elements that follow the end of this structure.


### -field ComponentActiveConditionCallback

A pointer to a  <a href="kernel.componentactiveconditioncallback">ComponentActiveConditionCallback</a> callback routine. PoFx calls this routine to notify the driver that the specified component completed a transition from the idle condition to the active condition.


### -field ComponentIdleConditionCallback

A pointer to a <a href="kernel.componentidleconditioncallback">ComponentIdleConditionCallback</a> callback routine. PoFx calls this routine to notify the driver that the specified component completed a transition from the active condition to the idle condition.


### -field ComponentCriticalTransitionCallback

A pointer to a <a href="kernel.componentcriticaltransitioncallback">ComponentCriticalTransitionCallback</a> callback routine. PoFx calls this routine to notify the driver that the specified component is about to make a transition between the idle condition and the active condition.


### -field ComponentIdleStateCallback

A pointer to a <a href="kernel.componentidlestatecallback">ComponentIdleStateCallback</a> callback routine. PoFx calls this routine to notify the driver of a pending change to the F<i>x</i> power state of the specified component.


### -field DeviceContext

A pointer to a PEP-defined device context. PoFx supplies this pointer as the first parameter in calls to the <i>ComponentActiveConditionCallback</i>, <i>ComponentIdleConditionCallback</i>, <i>ComponentCriticalTransitionCallback</i>, and <i>ComponentIdleStateCallback</i> routines. This context is opaque to PoFx.


### -field Components

The first element in an array of <a href="kernel.po_fx_component">PO_FX_COMPONENT</a> structures. Each element in the array describes the power attributes of a component in the device. If the array contains more than one element, the additional elements immediately follow the end of the <b>PO_FX_CORE_DEVICE</b> structure. The number of elements in the array is specified in the <b>ComponentCount</b> member of the <b>PO_FX_CORE_DEVICE</b> structure.


## -remarks
This structure is used by the <a href="kernel.pofxregistercoredevice">PoFxRegisterCoreDevice</a> routine.

A <i>core system resource</i> is a hardware device, such as a timer or an interrupt controller, that is managed by the Windows hardware abstraction layer (HAL).

For more information about component transitions between the active condition and the idle condition, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450935">Component-Level Power Management</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.componentactiveconditioncallback">ComponentActiveConditionCallback</a>
</dt>
<dt>
<a href="kernel.componentcriticaltransitioncallback">ComponentCriticalTransitionCallback</a>
</dt>
<dt>
<a href="kernel.componentidleconditioncallback">ComponentIdleConditionCallback</a>
</dt>
<dt>
<a href="kernel.componentidlestatecallback">ComponentIdleStateCallback</a>
</dt>
<dt>
<a href="kernel.po_fx_component">PO_FX_COMPONENT</a>
</dt>
<dt>
<a href="kernel.pofxregistercoredevice">PoFxRegisterCoreDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_CORE_DEVICE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

