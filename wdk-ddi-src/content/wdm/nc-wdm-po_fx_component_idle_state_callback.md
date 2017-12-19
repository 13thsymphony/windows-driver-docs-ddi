---
UID: NC.wdm.PO_FX_COMPONENT_IDLE_STATE_CALLBACK
title: PO_FX_COMPONENT_IDLE_STATE_CALLBACK
author: windows-driver-content
description: The ComponentIdleStateCallback callback routine notifies the driver of a pending change to the Fx power state of the specified component.
old-location: kernel\componentidlestatecallback.htm
old-project: kernel
ms.assetid: B98D14A1-7016-4299-9E7E-45E5EB6BE912
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ComponentIdleStateCallback
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IRQL <= DISPATCH_LEVEL.
req.product: Windows 10 or later.
---

# PO_FX_COMPONENT_IDLE_STATE_CALLBACK callback



## -description
The <i>ComponentIdleStateCallback</i> callback routine notifies the driver of a pending change to the Fx power state of the specified component.



## -prototype

````
PO_FX_COMPONENT_IDLE_STATE_CALLBACK ComponentIdleStateCallback;

VOID ComponentIdleStateCallback(
  _In_ PVOID Context,
  _In_ ULONG Component,
  _In_ ULONG State
)
{ ... }
````


## -parameters

### -param Context [in]

A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the <b>DeviceContext</b> member of the <a href="kernel.po_fx_device">PO_FX_DEVICE</a> structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.


### -param Component [in]

Specifies the component number. This parameter is an index into the <b>Components</b> array in the <b>PO_FX_DEVICE</b> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N-1.


### -param State [in]

Specifies the new Fx power state that the component will change to. If this parameter is zero, the new state is F0; if this parameter is one, the new state is F1; and so on.


## -returns
None.


## -remarks
When PoFx calls the driver's <i>ComponentIdleStateCallback</i> routine, the driver might need to prepare for the pending Fx state change. After any necessary preparations are completed, the driver must call the <a href="kernel.pofxcompleteidlestate">PoFxCompleteIdleState</a> routine to notify PoFx that the driver completed its response to the <i>ComponentIdleStateCallback</i> callback. The <b>PoFxCompleteIdleState</b> call can occur either before or after the <i>ComponentIdleStateCallback</i> routine returns.

If the component is to switch from F0 to a low-power Fx state in which the device will lose the hardware state of the component, the driver must save the component's hardware state before the transition to the new Fx state occurs. If the component is to switch from a low-power Fx state to F0, and the hardware state was previously saved, the driver should restore the hardware state after power is restored to the component.

For some devices, the power state of a component might be controlled in the device hardware. For these devices, the driver is typically responsible for changing the power state of the component. For other devices, the power state of a component might be controlled by hardware that is external to the device, and the driver typically must rely on PoFx to configure the power state of the component.

If the driver is responsible for configuring the power state of the component, the driver should change the power state in response to the <i>ComponentIdleStateCallback</i> callback. For a transition from F0 to a low-power Fx state, the component is in F0 on entry to the <i>ComponentIdleStateCallback</i> routine, and the driver must switch the component the new Fx state before calling <b>PoFxCompleteIdleState</b>. For a transition from a low-power Fx state to F0, the component is in the low-power Fx state on entry to the <i>ComponentIdleStateCallback</i> routine, and the driver must switch the component to F0 before calling <b>PoFxCompleteIdleState</b>.

If the driver is not responsible for configuring the power state of the component, the driver should assume that the component is always in the F0 state on entry to the <i>ComponentIdleStateCallback</i> routine. For a pending transition from F0 to a low-power Fx state, the transition to the new Fx state does not occur until after the driver calls <b>PoFxCompleteIdleState</b>. For a transition from a low-power Fx state to F0, the transition to F0 occurs before the <i>ComponentIdleStateCallback</i> routine is called.

PoFx never calls the <i>ComponentIdleStateCallback</i> routine to switch directly from one low-power Fx state to another low-power Fx state. For example, PoFx might need to switch a component from one low-power Fx state to another in response to a call to the <a href="kernel.pofxsetcomponentlatency">PoFxSetComponentLatency</a>, <a href="kernel.pofxsetcomponentresidency">PoFxSetComponentResidency</a>, or <a href="kernel.pofxsetcomponentwake">PoFxSetComponentWake</a> routine. In this case, PoFx first calls the <i>ComponentIdleStateCallback</i> routine to switch from the old Fx state to F0, and then calls the <i>ComponentIdleStateCallback</i> routine a second time to switch from F0 to the new Fx state.

To define a <i>ComponentIdleStateCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ComponentIdleStateCallback</i> callback routine that is named <code>MyComponentIdleStateCallback</code>, use the PO_FX_COMPONENT_IDLE_STATE_CALLBACK type as shown in this code example:

Then, implement your callback routine as follows:

The PO_FX_COMPONENT_IDLE_STATE_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the PO_FX_COMPONENT_IDLE_STATE_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in Windows 8 and later versions of Windows.

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
IRQL

</th>
<td width="70%">
Called at IRQL &lt;= DISPATCH_LEVEL.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pofxcompleteidlestate">PoFxCompleteIdleState</a>
</dt>
<dt>
<a href="kernel.pofxsetcomponentlatency">PoFxSetComponentLatency</a>
</dt>
<dt>
<a href="kernel.pofxsetcomponentresidency">PoFxSetComponentResidency</a>
</dt>
<dt>
<a href="kernel.pofxsetcomponentwake">PoFxSetComponentWake</a>
</dt>
<dt>
<a href="kernel.po_fx_device">PO_FX_DEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ComponentIdleStateCallback routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

