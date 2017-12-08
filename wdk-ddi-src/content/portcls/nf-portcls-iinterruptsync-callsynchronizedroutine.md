---
UID: NF.portcls.IInterruptSync.CallSynchronizedRoutine
title: IInterruptSync::CallSynchronizedRoutine
author: windows-driver-content
description: The CallSynchronizedRoutine method calls a routine that is not an interrupt service routine (ISR) but whose execution needs to be synchronized with ISRs.
old-location: audio\iinterruptsync_callsynchronizedroutine.htm
old-project: audio
ms.assetid: 9895ee9a-4d8c-4cd4-8df4-fedaf864a178
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IInterruptSync, CallSynchronizedRoutine, IInterruptSync::CallSynchronizedRoutine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IInterruptSync.CallSynchronizedRoutine
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.iface: IInterruptSync
---

# IInterruptSync::CallSynchronizedRoutine method



## -description
<p>The <code>CallSynchronizedRoutine</code> method calls a routine that is not an interrupt service routine (ISR) but whose execution needs to be synchronized with ISRs.</p>


## -syntax

````
NTSTATUS CallSynchronizedRoutine(
  [in] PINTERRUPTSYNCROUTINE Routine,
  [in] PVOID                 DynamicContext
);
````


## -parameters
<dl>

### -param Routine [in]

<dd>
<p>Pointer to the routine that is to be called. This routine will run exclusive of the object's ISR and all other routines that are synchronized through the object. Even on multiple-processor machines, routines that are synchronized by a given object will not run concurrently. This parameter is a function pointer of type PINTERRUPTSYNCROUTINE (see <a href="..\portcls\nn-portcls-iinterruptsync.md">IInterruptSync</a>).</p>
</dd>

### -param DynamicContext [in]

<dd>
<p>A context value to be passed to the routine.</p>
</dd>
</dl>

## -returns
<p><code>CallSynchronizedRoutine</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.</p>

## -remarks
<p>Execution of any registered ISR is guaranteed to be held off until the call to the routine that is passed to <code>CallSynchronizedRoutine</code> has completed.</p>

<p>Callers of <code>CallSynchronizedRoutine</code> must be running at an IRQL that is less than or equal to the level of the interrupt that is associated with the synchronization object. This interrupt was specified by the <a href="..\portcls\nf-portcls-pcnewinterruptsync.md">PcNewInterruptSync</a> function's <i>ResourceList</i> and <i>ResourceIndex</i> parameters.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>See Remarks section.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iinterruptsync.md">IInterruptSync</a>
</dt>
<dt>
<a href="..\portcls\nf-portcls-pcnewinterruptsync.md">PcNewInterruptSync</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IInterruptSync::CallSynchronizedRoutine method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
