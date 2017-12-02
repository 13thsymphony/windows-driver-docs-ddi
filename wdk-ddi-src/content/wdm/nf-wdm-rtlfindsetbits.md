---
UID: NF.wdm.RtlFindSetBits
title: RtlFindSetBits
author: windows-driver-content
description: The RtlFindSetBits routine searches for a range of set bits of a requested size within a bitmap.
old-location: kernel\rtlfindsetbits.htm
old-project: kernel
ms.assetid: 35add921-e5a2-4c18-83db-86150c43b034
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlFindSetBits
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
req.alt-api: RtlFindSetBits
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
req.iface: 
req.product: Windows 10 or later.
---

# RtlFindSetBits function



## -description
<p>The <b>RtlFindSetBits</b> routine searches for a range of set bits of a requested size within a bitmap. </p>


## -syntax

````
ULONG RtlFindSetBits(
  _In_ PRTL_BITMAP BitMapHeader,
  _In_ ULONG       NumberToFind,
  _In_ ULONG       HintIndex
);
````


## -parameters
<dl>

### -param BitMapHeader [in]

<dd>
<p>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. </p>
</dd>

### -param NumberToFind [in]

<dd>
<p>Specifies how many contiguous set bits will satisfy this request. </p>
</dd>

### -param HintIndex [in]

<dd>
<p>Specifies a zero-based bit position around which to start looking for a set bit range of the given size. </p>
</dd>
</dl>

## -returns
<p><b>RtlFindSetBits</b> either returns the zero-based starting bit index for a set bit range of the requested size, or it returns 0xFFFFFFFF if it cannot find such a range within the given bitmap variable. </p>

## -remarks
<p>For a successful call, the returned bit position is not necessarily equivalent to the given <i>HintIndex</i>. If necessary, <b>RtlFindSetBits</b> searches the whole bitmap to locate a set bit range of the requested size. However, it starts searching for the requested range near <i>HintIndex</i>, so callers can find such a range more quickly when they can supply appropriate hints about where to start looking. </p>

<p>Callers of <b>RtlFindSetBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindSetBits</b> can be called at any IRQL.</p>

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
<a href="..\wdm\nf-wdm-rtlarebitsset.md">RtlAreBitsSet</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlclearbits.md">RtlClearBits</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfindclearbits.md">RtlFindClearBits</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfindsetbitsandclear.md">RtlFindSetBitsAndClear</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlnumberofsetbits.md">RtlNumberOfSetBits</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFindSetBits routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
