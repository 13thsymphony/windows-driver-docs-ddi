---
UID: NF:wdm.PoFxIssueComponentPerfStateChangeMultiple
title: PoFxIssueComponentPerfStateChangeMultiple function
author: windows-driver-content
description: The PoFxIssueComponentPerfStateChangeMultiple routine submits a request to change the performance states in multiple performance state sets simultaneously for a device component.
old-location: kernel\pofxissuecomponentperfstatechangemultiple.htm
old-project: kernel
ms.assetid: 246211E7-89A9-4916-BF6E-5771B911CBA3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PoFxIssueComponentPerfStateChangeMultiple
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
req.alt-api: PoFxIssueComponentPerfStateChangeMultiple
req.alt-loc: Ntoskrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: <= APC_LEVEL or <= DISPATCH_LEVEL (See Remarks section)
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoFxIssueComponentPerfStateChangeMultiple function



## -description
The <b>PoFxIssueComponentPerfStateChangeMultiple</b> routine submits a request to change the performance states in multiple performance state sets simultaneously for a device component. 



## -syntax

````
VOID PoFxIssueComponentPerfStateChangeMultiple(
  _In_ POHANDLE                Handle,
  _In_ ULONG                   Flags,
  _In_ ULONG                   Component,
  _In_ ULONG                   PerfChangesCount,
  _In_ PO_FX_PERF_STATE_CHANGE PerfChanges[],
  _In_ PVOID                   Context
);
````


## -parameters

### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="..\wdm\nf-wdm-pofxregisterdevice.md">PoFxRegisterDevice</a> routine.


### -param Flags [in]

The flags that modify the behavior of the performance state change operation. Set this member to zero or to one of the following flag <b>PO_FX_FLAG_<i>XXX</i></b> bits:

These two flag bits are mutually exclusive. For more information, see Remarks.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param PO_FX_FLAG_BLOCKING
### -param 0x1

</td>
<td width="60%">
Make the condition change synchronous. If this flag is set, the routine that requests the condition change does not return control to the calling driver until the component hardware completes the transition to the new condition. This flag can be used only if the caller is running at IRQL &lt; DISPATCH_LEVEL.

</td>
</tr>
<tr>

### -param PO_FX_FLAG_ASYNC_ONLY
### -param 0x2

</td>
<td width="60%">
Make the condition change fully asynchronous. If this flag is set, the calling driver's callback routine is called from a thread other than the thread in which the routine that requests the condition change is called. Thus, the routine that requests the condition change always returns asynchronously without waiting for the callback to complete.

</td>
</tr>
</table>
 


### -param Component [in]

The index that identifies the component. This parameter is an index into the <b>Components</b> array in the <a href="..\wdm\ns-wdm-_po_fx_device_v1.md">PO_FX_DEVICE</a> structure that the device driver used to register the device with PoFx. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -param PerfChangesCount [in]

The number of performance state change requests contained in the <i>PerfChanges</i> array.


### -param PerfChanges [in]

The first element in an array of <a href="..\wdm\ns-wdm-_po_fx_perf_state_change.md">PO_FX_PERF_STATE_CHANGE</a> structures that represent the performance states the driver intends to transition to. Each array element represents a single performance state change request. 


### -param Context [in]

A pointer to the context for the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> callback routine. This parameter is optional. It is provided so that a driver or device context can be passed to the callback routine. If this parameter is not used, it must be set to NULL.


## -returns
None


## -remarks
A driver calls <b>PoFxIssueComponentPerfStateChangeMultiple</b>, the power management framework (PoFx) will request the platform extension plug-in (PEP) to place 
    the component's performance state sets in the specified performance states. This routine may be used with both discrete and range-based types of performance state sets. For more information about discrete and range-based performance state sets, see <a href="..\wdm\ne-wdm-_po_fx_perf_state_type.md">PO_FX_PERF_STATE_TYPE</a>.

If <i>Flags</i> = <b>PO_FX_FLAG_BLOCKING</b>, the <b>PoFxIssueComponentPerfStateChangeMultiple</b> call is synchronous. In this case, <b>PoFxIssueComponentPerfStateChangeMultiple</b> waits to return until the component completes the performance state transition. The driver's <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> routine is called to inform the driver that the component's performance state change is complete. This callback occurs in the same thread as the call to <b>PoFxIssueComponentPerfStateChangeMultiple</b>, and <b>PoFxIssueComponentPerfStateChangeMultiple</b> returns only after the <i>ComponentPerfStateCallback</i> callback returns.

If <i>Flags</i> = <b>PO_FX_FLAG_ASYNC_ONLY</b>, the <b>PoFxIssueComponentPerfStateChangeMultiple</b> call is asynchronous. In this case, <b>PoFxIssueComponentPerfStateChangeMultiple</b> schedules the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> routine to occur in another thread, and then returns without waiting for the callback to occur. The callback can occur before or after <b>PoFxIssueComponentPerfStateChangeMultiple</b> returns. The driver should rely on the <i>ComponentPerfStateCallback</i> routine to determine when the component completes the transition to the new performance state. 

The driver can set <i>Flags</i> = 0 to indicate that it does not care whether the <b>PoFxIssueComponentPerfStateChangeMultiple</b> call is synchronous or asynchronous. In this case, PoFx decides the synchronicity of the call  based on whether the PEP uses a synchronous or asynchronous request to issue the performance state change to the component.

If <i>Flags</i> = <b>PO_FX_FLAG_ASYNC_ONLY</b> or no flags are passed, this routine requires an IRQL of &lt;= DISPATCH_LEVEL. If <i>Flags</i> = <b>PO_FX_FLAG_BLOCKING</b>, this routine requires an IRQL of &lt;= APC_LEVEL.

This function will always result in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> routine regardless of the synchronicity of the call. Because the PEP may choose to deny the request to change the performance states, the driver must wait until receiving the callback before committing the performance states to hardware.

Only a single call of the <b>PoFxIssueComponentPerfStateChangeMultiple</b> routine  is allowed at a time per component, regardless of whether the call is synchronous or asynchronous. After issuing a performance state change request, the driver must wait until the <a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a> is received before calling this routine again, even if the request involves a different performance state set.  If this routine is called again before waiting until the <i>ComponentPerfStateCallback</i> is received, a bugcheck will occur.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 10.

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
Library

</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL or &lt;= DISPATCH_LEVEL (See Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/D5341D6D-7C71-43CB-9C70-7E939B32C33F">Device Performance State Management</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-pofxregistercomponentperfstates.md">PoFxRegisterComponentPerfStates</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-pofxissuecomponentperfstatechange.md">PoFxIssueComponentPerfStateChange</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn939353">ComponentPerfStateCallback</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_po_fx_perf_state_type.md">PO_FX_PERF_STATE_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoFxIssueComponentPerfStateChangeMultiple routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

