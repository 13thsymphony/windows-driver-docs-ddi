---
UID: NF.wdm.RtlFindFirstRunClear
title: RtlFindFirstRunClear
author: windows-driver-content
description: The RtlFindFirstRunClear routine searches for the initial contiguous range of clear bits within a given bitmap.
old-location: kernel\rtlfindfirstrunclear.htm
ms.assetid: 21e7e65c-b549-4997-b6dd-a95577edaa26
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: kernel
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlFindFirstRunClear
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
req.irql: <= APC_LEVEL (See Remarks section)
ms.keywords: RtlFindFirstRunClear
req.iface: 
req.product: Windows 10 or later.
---

# RtlFindFirstRunClear function



## -description
<p>The <b>RtlFindFirstRunClear</b> routine searches for the initial contiguous range of clear bits within a given bitmap. </p>


## -syntax

````
ULONG RtlFindFirstRunClear(
  _In_  PRTL_BITMAP BitMapHeader,
  _Out_ PULONG      StartingIndex
);
````


## -parameters
<dl>

### -param <i>BitMapHeader</i> [in]

<dd>
<p>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine. </p>
</dd>

### -param <i>StartingIndex</i> [out]

<dd>
<p>Pointer to a variable in which the starting index of the initial clear run in the bitmap is returned. This is a zero-based value indicating the bit position of the first clear bit in the returned range. Its value is meaningless if <b>RtlFindFirstRunClear</b> cannot find a run of clear bits. </p>
</dd>
</dl>

## -returns
<p><b>RtlFindFirstRunClear</b> returns either the number of bits in the run beginning at <i>StartingIndex</i>, or zero if it cannot find a run of clear bits within the bitmap. </p>

## -remarks
<p>A returned run can have a single clear bit. That is, once a clear bit is found, <b>RtlFindFirstRunClear</b> continues searching until it finds the next set bit, and then returns the number of clear bits in the run it found.</p>

<p>Callers of <b>RtlFindFirstRunClear</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindFirstRunClear</b> can be called at any IRQL.</p>

<p>A returned run can have a single clear bit. That is, once a clear bit is found, <b>RtlFindFirstRunClear</b> continues searching until it finds the next set bit, and then returns the number of clear bits in the run it found.</p>

<p>Callers of <b>RtlFindFirstRunClear</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindFirstRunClear</b> can be called at any IRQL.</p>

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
<p>Available starting with Windows 2000.</p>
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
<p>&lt;= APC_LEVEL (See Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561742">RtlAreBitsClear</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561873">RtlFindClearBits</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561875">RtlFindClearRuns</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561877">RtlFindFirstRunClear</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561879">RtlFindLastBackwardRunClear</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561881">RtlFindLongestRunClear</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561885">RtlFindNextForwardRunClear</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562775">RtlSetBits</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562034">RtlNumberOfClearBits</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFindFirstRunClear routine%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
