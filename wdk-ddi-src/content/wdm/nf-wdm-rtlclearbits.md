---
UID: NF.wdm.RtlClearBits
title: RtlClearBits
author: windows-driver-content
description: The RtlClearBits routine sets all bits in the specified range of bits in the bitmap to zero.
old-location: kernel\rtlclearbits.htm
old-project: kernel
ms.assetid: 2c332700-7778-4342-b99b-093142496624
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlClearBits
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
req.alt-api: RtlClearBits
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
req.irql: <= APC_LEVEL (See Remarks section.)
req.iface: 
req.product: Windows 10 or later.
---

# RtlClearBits function



## -description
<p>The <b>RtlClearBits</b> routine sets all bits in the specified range of bits in the bitmap to zero.</p>


## -syntax

````
VOID RtlClearBits(
  _In_ PRTL_BITMAP BitMapHeader,
  _In_ ULONG       StartingIndex,
  _In_ ULONG       NumberToClear
);
````


## -parameters
<dl>

### -param BitMapHeader [in]

<dd>
<p>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine.</p>
</dd>

### -param StartingIndex [in]

<dd>
<p>The index of the first bit in the bit range that is to be cleared. If the bitmap contains N bits, the bits are numbered from 0 to N-1.</p>
</dd>

### -param NumberToClear [in]

<dd>
<p>Specifies how many bits to clear. If the bitmap contains N bits, this parameter can be a value in the range 1 to (N - <i>StartingIndex</i>).</p>
</dd>
</dl>

## -returns
<p>This routine does not return a value.</p>

## -remarks
<p>If the <i>NumberToClear</i> parameter is zero, <b>RtlClearBits</b> simply returns control without clearing any bits.</p>

<p>The sum (<i>StartingIndex</i> + <i>NumberToClear</i>) must not exceed the <i>SizeOfBitMap</i> parameter value specified in the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> call that initialized the bitmap.</p>

<p>Callers of <b>RtlClearBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlClearBits</b> can be called at any IRQL.</p>

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
<p>&lt;= APC_LEVEL (See Remarks section.)</p>
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
<a href="..\wdm\nf-wdm-rtlclearallbits.md">RtlClearAllBits</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfindsetbits.md">RtlFindSetBits</a>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlClearBits routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
