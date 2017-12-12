---
UID: NF.ntifs.KeRemoveQueue
title: KeRemoveQueue function
author: windows-driver-content
description: The KeRemoveQueue routine gives the calling thread a pointer to a dequeued entry from the given queue object or allows the caller to wait, up to an optional timeout interval, on the queue object.
old-location: ifsk\keremovequeue.htm
old-project: ifsk
ms.assetid: 475e352a-b6ea-4e37-ad46-e94284caa105
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: KeRemoveQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeRemoveQueue
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
---

# KeRemoveQueue function



## -description
The <b>KeRemoveQueue</b> routine gives the calling thread a pointer to a dequeued entry from the given queue object or allows the caller to wait, up to an optional timeout interval, on the queue object. 



## -syntax

````
PLIST_ENTRY KeRemoveQueue(
  _Inout_  PRKQUEUE        Queue,
  _In_     KPROCESSOR_MODE WaitMode,
  _In_opt_ PLARGE_INTEGER  Timeout
);
````


## -parameters

### -param Queue [in, out]

Pointer to an initialized queue object for which the caller provides resident storage in nonpaged pool.


### -param WaitMode [in]

The processor mode in which the caller is waiting, which can be either <b>KernelMode</b> or <b>UserMode</b>. If anything on its stack might be accessed at IRQL &gt;= DISPATCH_LEVEL, the caller must specify <b>KernelMode</b>. 


### -param Timeout [in, optional]

Pointer to a variable that specifies the absolute or relative time, in units of 100 nanoseconds, at which the wait is to expire. If the value of <i>Timeout</i> is negative, the expiration time is relative to the current system time; otherwise, it is absolute. Absolute expiration times track any changes in system time; relative expiration times are not affected by system time changes. This pointer can be <b>NULL</b>. 


## -returns
<b>KeRemoveQueue</b> returns one of the following:


## -remarks
Callers of <b>KeRemoveQueue</b> should test whether its return value is STATUS_TIMEOUT or STATUS_USER_APC before accessing any entry members. Testing the return value of <b>KeRemoveQueue</b> against <b>NULL</b> is a programming error. 

Specifying a zero value for <i>*Timeout</i> indicates the caller's unwillingness to wait for an entry if the queue is currently empty. Specifying a <b>NULL</b><i>Timeout</i> pointer indicates the caller's willingness to wait indefinitely for an entry. 

If the <i>WaitMode</i> parameter is <b>UserMode</b>, the kernel stack can be swapped out during the wait. Consequently, a caller must never attempt to pass parameters on the stack when calling <b>KeRemoveQueue</b> with <i>WaitMode</i> set to <b>UserMode</b>.

Specifying <i>WaitMode</i> as <b>KernelMode</b> in a call to <b>KeRemoveQueue</b> prevents the calling thread's kernel stack from being swapped out, as well as preventing the delivery of user-mode asynchronous procedure calls (APC). It does not prevent the delivery of kernel-mode APCs, such as those used by the I/O Manager to complete IRPs, when a thread calls <b>KeRemoveQueue</b> from IRQL PASSIVE_LEVEL. Delivery of such a kernel-mode APC does not prevent the calling thread from waiting on the queue object nor from being dispatched for execution with an entry after the kernel APC has run. 

For more information about using driver-managed internal queues, see <a href="kernel.driver_managed_queues">Driver-Managed Queues</a>. 


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
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or FltKernel.h)</dt>
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
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.keinsertheadqueue">KeInsertHeadQueue</a>
</dt>
<dt>
<a href="ifsk.keinsertqueue">KeInsertQueue</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20KeRemoveQueue routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

