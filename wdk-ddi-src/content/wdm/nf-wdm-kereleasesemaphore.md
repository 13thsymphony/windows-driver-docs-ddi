---
UID: NF:wdm.KeReleaseSemaphore
title: KeReleaseSemaphore function
author: windows-driver-content
description: The KeReleaseSemaphore routine releases the specified semaphore object.
old-location: kernel\kereleasesemaphore.htm
old-project: kernel
ms.assetid: 357a97e6-cb19-43df-9b90-db199c712878
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeReleaseSemaphore
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeReleaseSemaphore
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeReleaseSemaphore function



## -description
The <b>KeReleaseSemaphore</b> routine releases the specified semaphore object. 



## -syntax

````
LONG KeReleaseSemaphore(
  _Inout_ PRKSEMAPHORE Semaphore,
  _In_    KPRIORITY    Increment,
  _In_    LONG         Adjustment,
  _In_    BOOLEAN      Wait
);
````


## -parameters

### -param Semaphore [in, out]

A pointer to an initialized semaphore object for which the caller provides the storage.


### -param Increment [in]

Specifies the priority increment to be applied if releasing the semaphore causes a wait to be satisfied.


### -param Adjustment [in]

Specifies a value to be added to the current semaphore count. This value must be positive.


### -param Wait [in]

Specifies whether the call to <b>KeReleaseSemaphore</b> is to be followed <u>immediately</u> by a call to one of the <b>KeWait<i>Xxx</i></b> routines. If <b>TRUE</b>, the <b>KeReleaseSemaphore</b> call must be followed by a call to <a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>, or <a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>. For more information, see the following Remarks section. 


## -returns
If the return value is zero, the previous state of the semaphore object is not-signaled. 


## -remarks
<b>KeReleaseSemaphore</b> supplies a run-time priority boost for waiting threads. If this call sets the semaphore to the signaled state, the semaphore count is augmented by the specified value. The caller can also specify whether it will call one of the <b>KeWait<i>Xxx</i></b> routines as soon as <b>KeReleaseSemaphore</b> returns control.

Releasing a semaphore object causes the semaphore count to be augmented by the value of the <i>Adjustment</i> parameter. If the resulting value is greater than the limit of the semaphore object, the count is not adjusted and an exception, STATUS_SEMAPHORE_LIMIT_EXCEEDED, is raised.

Augmenting the semaphore object count causes the semaphore to attain a signaled state, and an attempt is made to satisfy as many waits as possible on the semaphore object.

The <b>KeReleaseSemaphore</b> routine might temporarily raise the IRQL. If the <i>Wait</i> parameter is <b>FALSE</b>, the routine, before it returns, restores the IRQL to the original value that it had at the start of the call.

If <i>Wait</i> = <b>TRUE</b>, the routine returns without lowering the IRQL. In this case, the <b>KeReleaseSemaphore</b> call must be immediately followed by a <b>KeWait<i>Xxx</i></b> call. By setting <i>Wait</i> = <b>TRUE</b>, the caller can prevent an unnecessary context switch from occurring between the <b>KeReleaseSemaphore</b> call and the <b>KeWait<i>Xxx</i></b> call. The <b>KeWait<i>Xxx</i></b> routine, before it returns, restores the IRQL to its original value at the start of the <b>KeReleaseSemaphore</b> call. Although the IRQL disables context switches between the two calls, these calls cannot reliably be used as the start and end of an atomic operation. For example, between these two calls, a thread that is running at the same time on another processor might change the state of the semaphore object or of the target of the wait.

If the caller is executing at IRQL = DISPATCH_LEVEL or in an arbitrary thread context, the <i>Timeout</i> parameter to <b>KeWait<i>Xxx</i></b> must be zero.

For more information about semaphore objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563719">Semaphore Objects</a>.

Callers of <b>KeReleaseSemaphore</b> must be running at IRQL &lt;= DISPATCH_LEVEL provided that <i>Wait</i> is set to <b>FALSE</b>. Otherwise, the caller must be running at IRQL = PASSIVE_LEVEL.


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
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
See Remarks section.

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-keinitializesemaphore.md">KeInitializeSemaphore</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kereadstatesemaphore.md">KeReadStateSemaphore</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kewaitformultipleobjects.md">KeWaitForMultipleObjects</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553344">KeWaitForMutexObject</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kewaitforsingleobject.md">KeWaitForSingleObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeReleaseSemaphore routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

