---
UID: NF:wdm.PoFxQueryCurrentComponentPerfState
title: PoFxQueryCurrentComponentPerfState function
author: windows-driver-content
description: The PoFxQueryCurrentComponentPerfState routine retrieves the active performance state in a component's performance state set.
old-location: kernel\pofxquerycurrentcomponentperfstate.htm
old-project: kernel
ms.assetid: DFB59020-1F4A-4ABB-8BBE-85F9C8615249
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PoFxQueryCurrentComponentPerfState, PoFxQueryCurrentComponentPerfState routine [Kernel-Mode Driver Architecture], kernel.pofxquerycurrentcomponentperfstate, wdm/PoFxQueryCurrentComponentPerfState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
api_name:
-	PoFxQueryCurrentComponentPerfState
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# PoFxQueryCurrentComponentPerfState function
The <b>PoFxQueryCurrentComponentPerfState</b> routine retrieves the active performance state in a component's performance state set.

## Syntax

````
NTSTATUS PoFxQueryCurrentComponentPerfState(
  _In_ POHANDLE   Handle,
  _In_ ULONG      Flags,
  _In_ ULONG      Component,
  _In_ ULONG      SetIndex,
  _In_ PULONGLONG CurrentPerf
);
````

## Parameters

`Handle`

A handle that represents the registration of the device with power management framework (PoFx). The device driver previously received this handle from the <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> routine.

`Flags`

Set to 0. Currently, no flags are defined for this routine.

`Component`

The index that identifies the component whose performance state is being retrieved. This parameter is an index into the <b>Components</b> array in the <a href="..\wudfwdm\ns-wudfwdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

`SetIndex`

The index that identifies the performance state set whose performance is being queried. This parameter is an index into the <b>PerfStateSets</b> array in the <a href="..\wudfwdm\ns-wudfwdm-_po_fx_device_v1.md">PO_FX_COMPONENT_PERF_INFO</a> structure that the device driver used to register the component performance states with PoFx. If the <b>PerfStateSets</b> array contains N elements, performance state set indexes range from 0 to N–1.

`CurrentPerf`

A pointer to variable in which the current performance state for the specified performance state set is returned. For more information about the value that is returned, see Remarks.


## Return Value

<b>PoFxQueryCurrentComponentPerfState</b> returns <b>STATUS_SUCCESS</b> if the requested operation succeeds. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>STATUS_INVALID_PARAMETER</b></b></dt>
</dl>
</td>
<td width="60%">
The caller supplied an invalid index for the component or component state set.

</td>
</tr>
</table>

## Remarks

A driver can call the <b>PoFxQueryCurrentComponentPerfState</b> routine to retrieve the current performance state of a given performance state set for a component. If the call succeeds, the <i>CurrentPerf</i> parameter is overwritten with a pointer to a value that specifies the current performance state of the set. This value may be one of the following, depending on the contents of the <a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a> structure that the driver passed to the <a href="..\wdm\nf-wdm-pofxregistercomponentperfstates.md">PoFxRegisterComponentPerfStates</a> routine:

<ul>
<li>For a performance state set that represents a continuous distribution of performance states, this is a value between the <b>Minimum</b> and <b>Maximum</b> members of the <a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a> structure.</li>
<li>For a performance state set that represents a discrete number of performance states, this value is an index into the <b>States</b> member of the <a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a> structure .</li>
</ul>
This call always executes synchronously.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10.  |
| **Target Platform** | Universal |
| **Header** | wdm.h |
| **Library** | Ntoskrnl.lib |
| **DLL** | Ntoskrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-pofxregistercomponentperfstates.md">PoFxRegisterComponentPerfStates</a>



<a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a>



<a href="https://msdn.microsoft.com/D5341D6D-7C71-43CB-9C70-7E939B32C33F">Device Performance State Management</a>



<a href="..\wudfwdm\ns-wudfwdm-_po_fx_device_v1.md">PO_FX_COMPONENT_PERF_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoFxQueryCurrentComponentPerfState routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>