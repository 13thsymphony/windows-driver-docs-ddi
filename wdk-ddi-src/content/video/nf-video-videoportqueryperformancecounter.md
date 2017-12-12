---
UID: NF.video.VideoPortQueryPerformanceCounter
title: VideoPortQueryPerformanceCounter function
author: windows-driver-content
description: The VideoPortQueryPerformanceCounter function provides the finest-grained running count available in the system.
old-location: display\videoportqueryperformancecounter.htm
old-project: display
ms.assetid: 44e9fca2-54b1-427c-864d-f170a8a26f5e
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: VideoPortQueryPerformanceCounter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VideoPortQueryPerformanceCounter
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: Any level
req.product: Windows 10 or later.
---

# VideoPortQueryPerformanceCounter function



## -description
The <b>VideoPortQueryPerformanceCounter</b> function provides the finest-grained running count available in the system.



## -syntax

````
LONGLONG VideoPortQueryPerformanceCounter(
  _In_      PVOID     HwDeviceExtension,
  _Out_opt_ PLONGLONG PerformanceFrequency
);
````


## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param PerformanceFrequency [out, optional]

Specifies an optional pointer to a variable that is to receive the performance counter frequency.


## -returns
<b>VideoPortQueryPerformanceCounter</b> returns the performance counter value in units of ticks.


## -remarks
<b>VideoPortQueryPerformanceCounter</b> always returns a 64-bit integer representing the number of ticks. Accumulating the count begins when the system is booted. The count is in ticks; the frequency is reported by <i>PerformanceFrequency</i> if this optional parameter is supplied.

The resolution of the timer used to accumulate the current count can be obtained by specifying <i>PerformanceFrequency</i>. For example, if the returned <i>PerformanceFrequency</i> is 2 million, each tick is 1/2 millionth of a second. Each 1/<i>x</i> millionth increment of the count corresponds to one second of elapsed time.

<b>VideoPortQueryPerformanceCounter</b> is intended for time-stamping packets or for computing performance and capacity measurements. It is not intended for measuring elapsed time, for computing stalls or waits, or for iterations.

Use this routine as infrequently as possible. Depending on the platform, <b>VideoPortQueryPerformanceCounter</b> can disable system-wide interrupts for a minimal interval. Consequently, calling this routine frequently or repeatedly, as in an iteration, defeats its purpose of returning very fine-grained, running time-stamp information. Calling this routine too frequently can degrade I/O performance for the calling driver and for the system as a whole. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows XP and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
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