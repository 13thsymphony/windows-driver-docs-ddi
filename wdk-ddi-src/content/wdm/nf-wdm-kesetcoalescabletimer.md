---
UID: NF.wdm.KeSetCoalescableTimer
title: KeSetCoalescableTimer
author: windows-driver-content
description: The KeSetCoalescableTimer routine sets the initial expiration time and period of a timer object and specifies how much delay can be tolerated in the expiration times.
old-location: kernel\kesetcoalescabletimer.htm
old-project: kernel
ms.assetid: e053c120-8c43-4714-acf1-0648958eabb8
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KeSetCoalescableTimer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeSetCoalescableTimer
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
req.iface: 
req.product: Windows 10 or later.
---

# KeSetCoalescableTimer function



## -description
<p>The <b>KeSetCoalescableTimer</b> routine sets the initial expiration time and period of a timer object and specifies how much delay can be tolerated in the expiration times. </p>


## -syntax

````
BOOLEAN KeSetCoalescableTimer(
  _Inout_  PKTIMER       Timer,
  _In_     LARGE_INTEGER DueTime,
  _In_     ULONG         Period,
  _In_     ULONG         TolerableDelay,
  _In_opt_ PKDPC         Dpc
);
````


## -parameters
<dl>

### -param Timer [in, out]

<dd>
<p>A pointer to a timer object. This parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554250">KTIMER</a> structure, which is an opaque, system structure that represents the timer object. This object must have been previously initialized by the <a href="..\wdm\nf-wdm-keinitializetimerex.md">KeInitializeTimerEx</a> or <a href="..\wdm\nf-wdm-keinitializetimer.md">KeInitializeTimer</a> routine.</p>
</dd>

### -param DueTime [in]

<dd>
<p>Specifies an absolute or relative time at which the timer is to expire. If the value of the <i>DueTime</i> parameter is negative, the expiration time is relative to the current system time. Otherwise, the expiration time is absolute. The expiration time is expressed in system time units, which are 100-nanosecond intervals. Absolute expiration times track any changes that are made to the system clock. Relative expiration times are not affected by system clock changes.</p>
</dd>

### -param Period [in]

<dd>
<p>Specifies the interval between periodic timer expirations in milliseconds. The value of this parameter must not exceed MAXLONG. This parameter is optional and can be set to zero to indicate that the timer is nonperiodic.</p>
</dd>

### -param TolerableDelay [in]

<dd>
<p>Specifies a tolerance, in milliseconds, for the timer period that <i>Period</i> specifies and for the initial time interval that <i>DueTime</i> specifies. For a periodic timer, the time interval between two successive timer expirations will be in the range from (<i>Period</i> - <i>TolerableDelay</i>) to (<i>Period</i> + <i>TolerableDelay</i>). The initial expiration time will be in the range from <i>DueTime</i> to (<i>DueTime</i> + <i>TolerableDelay</i>). The <i>TolerableDelay</i> value cannot be negative.</p>
</dd>

### -param Dpc [in, optional]

<dd>
<p>A pointer to a DPC object. This parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure, which is an opaque, system structure that represents the DPC object. This object must have been previously initialized by the <a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a> routine. This parameter is optional and can be specified as <b>NULL</b> if the caller does not require a DPC.</p>
</dd>
</dl>

## -returns
<p><b>KeSetCoalescableTimer</b> returns <b>TRUE</b> if the timer object was already in the system timer queue. Otherwise, it returns <b>FALSE</b>. </p>

## -remarks
<p>This routine does the following:</p>

<p>Sets the timer to a nonsignaled state.</p>

<p>Associates the timer with the DPC, if a DPC is specified.</p>

<p>Cancels the timer if it is already active.</p>

<p>Makes the timer active and sets the due time and period of the timer to the specified values. The timer can expire immediately if the specified due time has already passed.</p>

<p>The <a href="..\wdm\nf-wdm-kesettimerex.md">KeSetTimerEx</a> routine is similar to <b>KeSetCoalescableTimer</b> but does not accept a <i>TolerableDelay</i> parameter. The <i>TolerableDelay</i> parameter of <b>KeSetCoalescableTimer</b> enables the caller to specify a tolerance for the timer period. A call to <b>KeSetCoalescableTimer</b> with <i>TolerableDelay</i> = 0 is the same as a call to <b>KeSetTimerEx</b>. In many instances, developers can easily modify existing drivers by replacing calls to <b>KeSetTimerEx</b> with calls to <b>KeSetCoalescableTimer</b>.</p>

<p>If two <b>KeSetCoalescableTimer</b> calls specify the same timer object, and the second call occurs before the <i>DueTime</i> that is specified for the first call expires, the second call implicitly cancels the timer from the first call. However, if a timer expiration from the first call has already enabled a DPC to run, the DPC might run after the timer is canceled. The second call replaces the pending expiration time from the first call with a new expiration time, and activates the timer again.</p>

<p>If the <i>Period</i> parameter is nonzero, the timer is periodic. For a periodic timer, the first timer expiration occurs at the time indicated by the <i>DueTime</i> parameter. Later expirations are separated by the interval that is specified by <i>Period</i>. If <i>Period</i> = 0, the timer is nonperiodic and expires at the time that is indicated by <i>DueTime</i>.</p>

<p>If the <i>Dpc</i> parameter is non-<b>NULL</b>, the routine creates an association between the specified DPC object and the timer object. After the timer expires, the timer service removes the timer object from the system timer queue and sets this object to a signaled state. If a DPC object is associated with the timer object, the timer service inserts the DPC object into the system DPC queue to run as soon as conditions allow.</p>

<p>Only one instance of a particular DPC object can be in the system DPC queue at a time. To avoid potential race conditions, avoid passing the same DPC object to both the <b>KeSetCoalescableTimer</b> and <a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a> routines.</p>

<p>Avoid changing the importance or the target processor of a DPC that is associated with an active timer. Either cancel the timer or make sure that the timer has expired before you call a routine such as <a href="..\wdm\nf-wdm-kesetimportancedpc.md">KeSetImportanceDpc</a> or <a href="..\wdm\nf-wdm-kesettargetprocessordpcex.md">KeSetTargetProcessorDpcEx</a> to change the DPC settings. For example, if a driver updates the target processor of a DPC while a timer enables the DPC to run, the DPC might run on an arbitrary processor.</p>

<p>A periodic timer automatically restarts as soon as it expires. Therefore, in a multiprocessor system, the DPC for a periodic timer might be running on two or more processors at the same time.</p>

<p>Drivers must cancel any active timers in their <a href="kernel.unload">Unload</a> routines. Call the <a href="..\wdm\nf-wdm-kecanceltimer.md">KeCancelTimer</a> routine to cancel a timer. If a DPC is associated with a timer that is periodic or that might recently have expired, a driver must wait (for example, by calling the <a href="..\wdm\nf-wdm-keflushqueueddpcs.md">KeFlushQueuedDpcs</a> routine) to free the DPC and its associated data until all pending DPC executions on all processors finish. </p>

<p><b>KeSetCoalescableTimer</b> uses the <i>TolerableDelay</i> parameter to perform timer coalescing. That is, the routine adjusts the expiration times for the timer to coincide with the expiration times of other software timers. Timer coalescing helps increase the length of idle periods so that the operating system can reduce power consumption and improve energy efficiency.</p>

<p>To use timer coalescing effectively, a caller should specify a <i>TolerableDelay</i> value of at least 32 milliseconds. This value equals two default system clock intervals of 15.6 milliseconds. If you can, use a larger <i>TolerableDelay</i> value, such as 100 milliseconds.</p>

<p>Try to specify the <i>Period</i> and <i>TolerableDelay</i> values in multiples of 50 milliseconds. Typical <i>Period</i> values are 50, 100, 250, 500, and 1000 milliseconds. Typical <i>TolerableDelay</i> values are 50, 100, 150, and 250 milliseconds.</p>

<p>Typically, a timer with a large <i>Period</i> value can use a proportionally large <i>TolerableDelay</i> value. For example, a timer with <i>Period</i> = 500 milliseconds might use <i>TolerableDelay</i> = 50 milliseconds, but a timer with <i>Period</i> = 10 seconds might use <i>TolerableDelay</i> = 1 second.</p>

<p>Expiration times are measured relative to the system clock, and the accuracy with which the operating system can detect when a timer expires is limited by the granularity of the system clock. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/jj602805">Timer Accuracy</a>.</p>

<p>For more information about timer objects, see <a href="https://msdn.microsoft.com/b58487de-6e9e-45f4-acb8-9233c8718ee2">Timer Objects and DPCs</a>. For more information about timer coalescing, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=116598">Windows Timer Coalescing</a> white paper on the WHDC website. </p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 7.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kecanceltimer.md">KeCancelTimer</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keflushqueueddpcs.md">KeFlushQueuedDpcs</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializetimer.md">KeInitializeTimer</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinitializetimerex.md">KeInitializeTimerEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesetimportancedpc.md">KeSetImportanceDpc</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesettargetprocessordpcex.md">KeSetTargetProcessorDpcEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kesettimerex.md">KeSetTimerEx</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554250">KTIMER</a>
</dt>
<dt>
<a href="kernel.unload">Unload</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeSetCoalescableTimer routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
