---
UID: NF.ntifs.RtlTimeToSecondsSince1980
title: RtlTimeToSecondsSince1980
author: windows-driver-content
description: The RtlTimeToSecondsSince1980 routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1980.
old-location: ifsk\rtltimetosecondssince1980.htm
old-project: ifsk
ms.assetid: 76a0fc34-a3e9-4f97-9c60-e7d179b1e6c3
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RtlTimeToSecondsSince1980
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlTimeToSecondsSince1980
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
req.irql: < DISPATCH_LEVEL
req.iface: 
---

# RtlTimeToSecondsSince1980 function



## -description
<p>The <b>RtlTimeToSecondsSince1980</b> routine converts a given absolute system time value to the elapsed time, in seconds, since the beginning of 1980. </p>


## -syntax

````
BOOLEAN RtlTimeToSecondsSince1980(
  _In_  PLARGE_INTEGER Time,
  _Out_ PULONG         ElapsedSeconds
);
````


## -parameters
<dl>

### -param <i>Time</i> [in]

<dd>
<p>Pointer to a variable that specifies the system time value to be converted. The approximate valid range for this variable begins at 1980 and ends around 2115. </p>
</dd>

### -param <i>ElapsedSeconds</i> [out]

<dd>
<p>Pointer to a caller-allocated variable that receives the corresponding number of seconds since midnight, December 31, 1979. </p>
</dd>
</dl>

## -returns
<p><b>RtlTimeToSecondsSince1980</b> returns <b>TRUE</b> if the input <i>Time</i> falls within a range that it can accurately convert to <i>ElapsedSeconds</i>. </p>

## -remarks
<p>The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The basis for system time is the start of 1601. The value that is processed by <b>RtlTimeToSecondsSince1980</b> is truncated to one-millisecond resolution. </p>

<p>For more information about converting time values, see <a href="kernel.data_conversions">Data Conversions</a>. </p>

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
<dt>Ntifs.h (include Ntifs.h)</dt>
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
<p>&lt; DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-rtlsecondssince1970totime.md">RtlSecondsSince1980ToTime</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtltimefieldstotime.md">RtlTimeFieldsToTime</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtltimetosecondssince1980.md">RtlTimeToSecondsSince1970</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtltimetotimefields.md">RtlTimeToTimeFields</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlTimeToSecondsSince1980 routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
