---
UID: NC.wdm.PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK
title: PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK
author: windows-driver-content
description: The ComponentIdleConditionCallback callback routine notifies the driver that the specified component completed a transition from the active condition to the idle condition.
old-location: kernel\componentidleconditioncallback.htm
old-project: kernel
ms.assetid: 785DF693-DB7A-4675-9F33-200F17093333
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ComponentIdleConditionCallback
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
req.iface: 
req.product: Windows 10 or later.
---

# PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK callback



## -description
<p>The <i>ComponentIdleConditionCallback</i> callback routine notifies the driver that the specified component completed a transition from the active condition to the idle condition.</p>


## -prototype

````
PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK ComponentIdleConditionCallback;

VOID ComponentIdleConditionCallback(
  _In_ PVOID Context,
  _In_ ULONG Component
)
{ ... }
````


## -parameters
<dl>

### -param Context [in]

<dd>
<p>A pointer to the device context. The device driver uses this context to store information about the current power state of the device. The device driver specified this pointer in the <b>DeviceContext</b> member of the <a href="kernel.po_fx_device">PO_FX_DEVICE</a> structure that the driver used to register the device with the power management framework (PoFx). This context is opaque to PoFx.</p>
</dd>

### -param Component [in]

<dd>
<p>The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <b>PO_FX_DEVICE</b> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>When the driver no longer needs to access a component that is in the active condition, the driver should call the <a href="..\wdm\nf-wdm-pofxidlecomponent.md">PoFxIdleComponent</a> routine to switch the component to the idle condition. In response to the <b>PoFxIdleComponent</b> call, PoFx initiates the transition to the idle condition, and then calls the <i>ComponentIdleConditionCallback</i> routine to notify the driver when this transition is complete.</p>

<p>The driver must call <b>PoFxCompleteIdleCondition</b> in response to every <i>ComponentIdleConditionCallback</i> callback. The <b>PoFxCompleteIdleCondition</b> call can occur either during the <i>ComponentIdleConditionCallback</i> callback or after the callback returns. The driver should complete any work that requires access to the hardware component before the call to <b>PoFxCompleteIdleCondition</b>. After this call, the component might not stay in the F0 power state.</p>

<p>A component can be safely accessed only when the component is in the active condition. Do not rely on the Fx power state of a component to determine whether the component can be accessed. If the component is in the F0 state and is in the idle condition, the component might be about to switch to another Fx state.</p>

<p>To define a <i>ComponentIdleConditionCallback</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ComponentIdleConditionCallback</i> callback routine that is named <code>MyComponentIdleConditionCallback</code>, use the PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK type as shown in this code example:</p>

<p>Then, implement your callback routine as follows:</p>

<p>The PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the PO_FX_COMPONENT_IDLE_CONDITION_CALLBACK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Called at IRQL &lt;= DISPATCH_LEVEL.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-pofxcompleteidlecondition.md">PoFxCompleteIdleCondition</a>
</dt>
<dt>
<a href="kernel.po_fx_device">PO_FX_DEVICE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ComponentIdleConditionCallback routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
