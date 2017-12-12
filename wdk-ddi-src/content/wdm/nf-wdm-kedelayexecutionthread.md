---
UID: NF.wdm.KeDelayExecutionThread
title: KeDelayExecutionThread function
author: windows-driver-content
description: The KeDelayExecutionThread routine puts the current thread into an alertable or nonalertable wait state for a specified interval.
old-location: kernel\kedelayexecutionthread.htm
old-project: kernel
ms.assetid: fe8dc704-3baf-4955-85fe-bba19181dbbf
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: KeDelayExecutionThread
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
req.alt-api: KeDelayExecutionThread
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlKeApcLte1, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# KeDelayExecutionThread function



## -description
The <b>KeDelayExecutionThread</b> routine puts the current thread into an alertable or nonalertable wait state for a specified interval. 



## -syntax

````
NTSTATUS KeDelayExecutionThread(
  _In_ KPROCESSOR_MODE WaitMode,
  _In_ BOOLEAN         Alertable,
  _In_ PLARGE_INTEGER  Interval
);
````


## -parameters

### -param WaitMode [in]

Specifies the processor mode in which the caller is waiting, which can be either <b>KernelMode</b> or <b>UserMode</b>. Lower-level drivers should specify <b>KernelMode</b>.


### -param Alertable [in]

Specifies <b>TRUE</b> if the wait is alertable. Lower-level drivers should specify <b>FALSE</b>.


### -param Interval [in]

Specifies the absolute or relative time, in units of 100 nanoseconds, for which the wait is to occur. A negative value indicates relative time. Absolute expiration times track any changes in system time; relative expiration times are not affected by system time changes.


## -returns
<b>KeDelayExecutionThread</b> returns one of the following values that describes how the delay was completed:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The delay completed because the specified interval elapsed.
<dl>
<dt><b>STATUS_ALERTED</b></dt>
</dl>The delay completed because the thread was alerted.
<dl>
<dt><b>STATUS_USER_APC</b></dt>
</dl>A user-mode APC was delivered before the specified <i>Interval </i>expired.

 

Note that the NT_SUCCESS macro recognizes all of these status values as "success" values.


## -remarks
The expiration time is computed and the current thread is put in a wait state. When the specified interval has passed, the thread exits the wait state and is put in the ready state, becoming eligible for execution.

The <i>Alertable</i> parameter determines when the thread can be alerted and its wait state consequently aborted. For additional information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565592">Waits and APCs</a>.

If the <i>WaitMode</i> parameter is <b>UserMode</b>, the kernel stack can be swapped out during the wait. Consequently, a caller must <u>never</u> attempt to pass parameters on the stack when calling <b>KeDelayExecutionThread</b> using the <b>UserMode</b> argument.

It is especially important to check the return value of <b>KeDelayExecutionThread</b> when the <i>WaitMode</i> parameter is <b>UserMode</b> or <i>Alertable</i> is <b>TRUE</b>, because <b>KeDelayExecutionThread</b> might return early with a status of STATUS_USER_APC or STATUS_ALERTED.

All long term waits that can be aborted by a user should be <b>UserMode</b> waits and <i>Alertable</i> should be set to <b>FALSE</b>.

Where possible, <i>Alertable</i> should be set to <b>FALSE</b> and <i>WaitMode</i> should be set to <b>KernelMode</b>, in order to reduce driver complexity. The principal exception to this guideline is when the wait is a long-term wait.

The expiration time of the delay is expressed as either an absolute time at which the delay is to expire, or a time relative to the current system time. If the <i>Interval</i> parameter value is positive, the expiration time is an absolute time. If this value is negative, the expiration time is a relative time.

Expiration times are measured relative to the system clock, and the accuracy with which the operating system can detect when a timer expires is limited by the granularity of the system clock. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj602805">Timer Accuracy</a>.


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
&lt;= APC_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.wdm_irqlkeapclte1">IrqlKeApcLte1</a>, <a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.kequerysystemtime">KeQuerySystemTime</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeDelayExecutionThread routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

