---
UID: NF.ntifs.RtlSecondsSince1980ToTime
title: RtlSecondsSince1980ToTime
author: windows-driver-content
description: The RtlSecondsSince1980ToTime routine converts the elapsed time, in seconds, since the beginning of 1980 to an absolute system time value.
old-location: ifsk\rtlsecondssince1980totime.htm
old-project: ifsk
ms.assetid: 2552df19-424e-43ba-9c8d-431123353d4a
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RtlSecondsSince1980ToTime
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
req.alt-api: RtlSecondsSince1980ToTime
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

# RtlSecondsSince1980ToTime function



## -description
<p>The <b>RtlSecondsSince1980ToTime</b> routine converts the elapsed time, in seconds, since the beginning of 1980 to an absolute system time value. </p>


## -syntax

````
VOID RtlSecondsSince1980ToTime(
  _In_  ULONG          ElapsedSeconds,
  _Out_ PLARGE_INTEGER Time
);
````


## -parameters
<dl>

### -param <i>ElapsedSeconds</i> [in]

<dd>
<p>Number of seconds from midnight, December 31, 1979, to the current date and time. </p>
</dd>

### -param <i>Time</i> [out]

<dd>
<p>Pointer to a caller-allocated variable that receives the corresponding current system time. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The basis for system time is the start of 1601. The value returned by <b>RtlSecondsSince1980ToTime</b> is truncated to one-millisecond resolution. </p>

<p>For more information about converting time values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542994">Data Conversions</a>. </p>

<p>The absolute system time is a LARGE_INTEGER value, accurate to 100-nanosecond resolution, assuming an accurate hardware clock. The basis for system time is the start of 1601. The value returned by <b>RtlSecondsSince1980ToTime</b> is truncated to one-millisecond resolution. </p>

<p>For more information about converting time values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542994">Data Conversions</a>. </p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553204">RtlSecondsSince1970ToTime</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562879">RtlTimeFieldsToTime</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553244">RtlTimeToSecondsSince1980</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562884">RtlTimeToTimeFields</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlSecondsSince1980ToTime routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
