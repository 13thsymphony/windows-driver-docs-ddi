---
UID: NF.ntifs.ZwWaitForSingleObject
title: ZwWaitForSingleObject function
author: windows-driver-content
description: The ZwWaitForSingleObject routine waits until the specified object attains a state of Signaled. An optional time-out can also be specified.
old-location: kernel\zwwaitforsingleobject.htm
old-project: kernel
ms.assetid: 5eea0877-329d-4fa3-847e-365d6a545b07
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: ZwWaitForSingleObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwWaitForSingleObject,NtWaitForSingleObject
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs, SpNoWait
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
---

# ZwWaitForSingleObject function



## -description
The <b>ZwWaitForSingleObject</b> routine waits until the specified object attains a state of Signaled. An optional time-out can also be specified.



## -syntax

````
NTSTATUS ZwWaitForSingleObject(
  _In_     HANDLE         Handle,
  _In_     BOOLEAN        Alertable,
  _In_opt_ PLARGE_INTEGER Timeout
);
````


## -parameters

### -param Handle [in]

A handle to the object.


### -param Alertable [in]

A boolean value that specifies whether the wait is alertable.


### -param Timeout [in, optional]

An optional pointer to a time-out value that specifies the absolute or relative time at which the wait is to be completed. A negative value specifies an interval relative to the current time. The value should be expressed in units of 100 nanoseconds. Absolute expiration times track any changes in the system time. Relative expiration times are not affected by system time changes.


## -returns
<b>ZwWaitForSingleObject</b> can return one of the following possible status codes:
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The caller did not have the required privileges to the event specified by the <i>Handle</i> parameter.
<dl>
<dt><b>STATUS_ALERTED</b></dt>
</dl>The wait was aborted to deliver an alert to the current thread.
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>The supplied <i>Handle</i> parameter was invalid.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The specified object satisfied the wait.
<dl>
<dt><b>STATUS_TIMEOUT</b></dt>
</dl>A time-out occurred before the object was set to a signaled state. This value can be returned when the specified set of wait conditions cannot be immediately met and the <i>Timeout</i> parameter is set to zero.
<dl>
<dt><b>STATUS_USER_APC</b></dt>
</dl>The wait was aborted to deliver a user APC to the current thread.

 

Note that the NT_SUCCESS macro recognizes the STATUS_ALERTED, STATUS_SUCCESS, STATUS_TIMEOUT, and STATUS_USER_APC status values as "success" values.


## -remarks
<b>ZwWaitForSingleObject</b> waits until the specified object attains a state of Signaled. An optional timeout can also be specified. <b>ZwWaitForSingleObject</b> examines the current state of the specified object to determine whether the wait can be satisfied immediately. If so, actions are performed. Otherwise, the current thread is put in a waiting state and a new thread is selected for execution on the current processor.

If a <i>Timeout</i> parameter is not specified, then the wait will not be satisfied until the object attains a state of Signaled. If a <i>Timeout</i> parameter is specified, and the object has not attained a state of Signaled when the time-out expires, then the wait is automatically satisfied. If an explicit <i>Timeout</i> value of zero is specified, then no wait will occur if the wait cannot be satisfied immediately. A <i>Timeout</i> value of zero allows the testing of a set of wait conditions and for the conditional performance of any side effects if the wait can be immediately satisfied, as in the acquisition of a mutex. The wait can also be specified as alertable.

The <i>Alertable</i> parameter specifies whether the thread can be alerted and its wait state consequently aborted. If the value of this parameter is <b>FALSE</b> then the thread cannot be alerted. The only exception to this rule is that of a terminating thread. Under certain circumstances a terminating thread can be alerted while it is in the process of winding down. A thread is automatically made alertable, for instance, when terminated by a user with a CTRL+C.

If the value of <i>Alertable</i>is <b>TRUE</b> and one of the following conditions is present, the thread will be alerted:

If the origin of the alert is an internal, undocumented kernel-mode routine used to alert threads.

The origin of the alert is a user-mode APC.

In the first of these two cases, the thread's wait is satisfied with a completion status of STATUS_ALERTED. In the second case, it is satisfied with a completion status of STATUS_USER_APC.

The thread must be alertable for a user-mode APC to be delivered. This is not the case for kernel-mode APCs. A kernel-mode APC can be delivered and executed even though the thread is not alerted. Once the APC's execution completes, the thread's wait resumes. A thread is never alerted, nor is its wait aborted, by the delivery of a kernel-mode APC.

The delivery of kernel-mode APCs to a waiting thread does not depend on whether the thread can be alerted. If the kernel-mode APC is a special kernel-mode APC, then the APC is delivered provided that the IRQL is less than APC_LEVEL. If the kernel-mode APC is a normal kernel-mode APC, then the APC is delivered provided that the following three conditions hold: (1) the IRQL is less than APC_LEVEL, (2) no kernel APC is in progress, and (3) the thread is not in a critical section.

If the handle passed to <b>ZwWaitForSingleObject</b> refers to a mutex, the APC delivery is the same as for all other dispatcher objects during the wait. However, once <b>ZwWaitForSingleObject</b> returns with STATUS_SUCCESS and the thread actually holds the mutex, only special kernel-mode APCs are delivered. Delivery of all other APCs, both kernel-mode and user-mode, is disabled. This restriction on the delivery of APCs persists until the mutex is released.

It is especially important to check the return value of <b>ZwWaitForSingleObject</b> when the <i>Alertable</i> parameter is <b>TRUE</b>, because <b>ZwWaitForSingleObject</b> might return early with a status of STATUS_USER_APC or STATUS_ALERTED.

All long term waits can be aborted by a user if the <i>Alertable</i> parameter is set to <b>FALSE</b>.

For additional information, see <a href="https://msdn.microsoft.com/b967beec-922c-4acf-a578-c476ce024fdb">Do Waiting Threads Receive Alerts and APCs?</a>


Callers of <b>ZwWaitForSingleObject</b> must be running at IRQL less than or equal to DISPATCH_LEVEL. Usually, the caller must be running at IRQL PASSIVE_LEVEL and in a nonarbitrary thread context. A call while running at IRQL DISPATCH_LEVEL is valid if and only if the caller specifies a <i>Timeout</i> parameter of zero. That is, a driver must not wait for a nonzero interval at IRQL equal to DISPATCH_LEVEL.

Time-out intervals are measured relative to the system clock, and the accuracy of the time-out measurement is limited by the granularity of the system clock. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj602805">Timer Accuracy</a>.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.


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
Available starting with Windows XP.

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
PASSIVE_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>, <a href="devtest.storport_spnowait">SpNoWait</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.iocreatenotificationevent">IoCreateNotificationEvent</a>
</dt>
<dt>
<a href="kernel.iocreatesynchronizationevent">IoCreateSynchronizationEvent</a>
</dt>
<dt>
<a href="kernel.keclearevent">KeClearEvent</a>
</dt>
<dt>
<a href="kernel.keresetevent">KeResetEvent</a>
</dt>
<dt>
<a href="kernel.kesetevent">KeSetEvent</a>
</dt>
<dt>
<a href="kernel.kewaitforsingleobject">KeWaitForSingleObject</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="kernel.zwclose">ZwClose</a>
</dt>
<dt>
<a href="kernel.zwcreateevent">ZwCreateEvent</a>
</dt>
<dt>
<a href="kernel.zwsetevent">ZwSetEvent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwWaitForSingleObject routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

