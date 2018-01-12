---
UID: NF:wdm.KeQueryPerformanceCounter
title: KeQueryPerformanceCounter function
author: windows-driver-content
description: The KeQueryPerformanceCounter routine retrieves the current value and frequency of the performance counter.Use KeQueryPerformanceCounter to acquire high resolution (&lt;1us) time stamps for time interval measurements.
old-location: kernel\kequeryperformancecounter.htm
old-project: kernel
ms.assetid: ee1dbd20-5502-4448-b39a-4629ddc73d01
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeQueryPerformanceCounter
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
req.alt-api: KeQueryPerformanceCounter
req.alt-loc: Hal.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: Hal.dll
req.irql: Any level
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# KeQueryPerformanceCounter function



## -description
The <b>KeQueryPerformanceCounter</b> routine retrieves the current value and frequency of the performance counter.

Use <b>KeQueryPerformanceCounter</b> to acquire high resolution (&lt;1us) time stamps for time interval measurements.



## -syntax

````
LARGE_INTEGER KeQueryPerformanceCounter(
  _Out_opt_ PLARGE_INTEGER PerformanceFrequency
);
````


## -parameters

### -param PerformanceFrequency [out, optional]

A pointer to a variable to which <b>KeQueryPerformanceCounter</b> writes the performance counter frequency, in ticks per second. This parameter is optional and can be NULL if the caller does not need the counter frequency value.


## -returns
<b>KeQueryPerformanceCounter</b> returns the performance counter value in units of ticks.


## -remarks
<b>KeQueryPerformanceCounter</b> returns a 64-bit integer that represents the current value of a high-resolution monotonically nondecreasing counter. 

To obtain the frequency of the performance counter, specify a non-<b>NULL</b> pointer value for the <i>PerformanceFrequency</i> parameter. The frequency of the performance counter is fixed at system boot and is consistent across all processors. Therefore, a driver can cache the frequency of the performance counter during initialization.  

For more info about this function and its usage, see <a href="https://msdn.microsoft.com/D66E0FC2-3AF2-489B-B4B5-78648905B77B">Acquiring high-resolution time stamps</a>. 


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
<dt>Hal.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Hal.dll</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-kequeryinterrupttime.md">KeQueryInterruptTime</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kequerytickcount.md">KeQueryTickCount</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kequerytimeincrement.md">KeQueryTimeIncrement</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/08169390-940b-4110-813a-249d107cc953">QueryPerformanceCounter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f69367a4-0516-4033-81e3-90d4c5270a1e">QueryPerformanceFrequency</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryPerformanceCounter routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

