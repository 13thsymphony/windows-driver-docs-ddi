---
UID: NF.ntifs.RtlFillMemoryUlonglong~r1
title: RtlFillMemoryUlonglong
author: windows-driver-content
description: The RtlFillMemoryUlonglong routine fills a given range of memory with one or more repetitions of a given ULONGLONG value.
old-location: ifsk\rtlfillmemoryulonglong.htm
old-project: ifsk
ms.assetid: b5604cdb-084e-431a-b413-020e8213a18f
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RtlFillMemoryUlonglong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: For AMD64 systems, this routine is available on Microsoft Windows 2000 and later. For non-AMD64 systems, this routine is available on Windows 7 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlFillMemoryUlonglong
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
req.irql: See Remarks section.
req.iface: 
---

# RtlFillMemoryUlonglong function



## -description
<p>The <b>RtlFillMemoryUlonglong</b> routine fills a given range of memory with one or more repetitions of a given ULONGLONG value. </p>


## -syntax

````
VOID RtlFillMemoryUlonglong(
  _Out_ PVOID     Destination,
  _In_  SIZE_T    Length,
  _In_  ULONGLONG Pattern
);
````


## -parameters
<dl>

### -param <i>Destination</i> [out]

<dd>
<p>Pointer to the start of the range of memory to be filled. This address must be ULONGLONG-aligned.</p>
</dd>

### -param <i>Length</i> [in]

<dd>
<p>Number of bytes to fill. This value must be a multiple of <b>sizeof(</b>ULONGLONG<b>)</b>. (Note: SIZE_T is defined in <i>basetsd.h</i>.)</p>
</dd>

### -param <i>Pattern</i> [in]

<dd>
<p>ULONGLONG value with which to fill the range starting at <i>Destination</i> and extending for <i>Length</i> bytes.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If the range of memory starting at <i>Destination</i> is nonpaged, the caller can be running at any IRQL. Otherwise, callers of <b>RtlFillMemoryUlonglong</b> must be running at IRQL &lt; DISPATCH_LEVEL.</p>

<p>For more information about managing buffered data and initializing driver-allocated buffers, see <a href="kernel.buffered_data_and_buffer_initialization">Buffered Data and Buffer Initialization</a>. </p>

<p>For AMD64 systems, this routine is a macro.  For non-AMD64 systems, this routine is contained in Ntoskrnl.lib.</p>

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
<p>For AMD64 systems, this routine is available on Microsoft Windows 2000 and later. For non-AMD64 systems, this routine is available on Windows 7 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or FltKernel.h)</dt>
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
<p>See Remarks section.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlfillmemory.md">RtlFillMemory</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlfillmemoryulong.md">RtlFillMemoryUlong</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlzeromemory.md">RtlZeroMemory</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlFillMemoryUlonglong routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
