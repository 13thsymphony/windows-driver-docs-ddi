---
UID: NF:wdm.RtlAreBitsClear
title: RtlAreBitsClear function
author: windows-driver-content
description: The RtlAreBitsClear routine determines whether a given range of bits within a bitmap variable is clear.
old-location: kernel\rtlarebitsclear.htm
old-project: kernel
ms.assetid: f4092f06-3ed7-4153-8498-0fdfac958a1e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlAreBitsClear
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
req.alt-api: RtlAreBitsClear
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlAreBitsClear function



## -description
The <b>RtlAreBitsClear</b> routine determines whether a given range of bits within a bitmap variable is clear. 



## -syntax

````
BOOLEAN RtlAreBitsClear(
  _In_ PRTL_BITMAP BitMapHeader,
  _In_ ULONG       StartingIndex,
  _In_ ULONG       Length
);
````


## -parameters

### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine. 


### -param StartingIndex [in]

Specifies the start of the bit range to be tested. This is a zero-based value indicating the position of the first bit in the range. 


### -param Length [in]

Specifies how many bits to test. 


## -returns
<b>RtlAreBitsClear</b> returns <b>TRUE</b> if <i>Length </i>consecutive bits beginning at <i>StartingIndex</i> are clear (that is, all the bits from <i>StartingIndex </i>to (<i>StartingIndex </i>+ <i>Length</i>) -1). It returns <b>FALSE</b> if any bit in the given range is set, if the given range is not a proper subset of the bitmap, or if the given <i>Length</i> is zero. 


## -remarks
Callers of <b>RtlAreBitsClear</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlAreBitsClear</b> can be called at any IRQL.


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
&lt;= APC_LEVEL (See Remarks section)

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
<a href="..\wdm\nf-wdm-rtlcheckbit.md">RtlCheckBit</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlclearallbits.md">RtlClearAllBits</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfindclearbits.md">RtlFindClearBits</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfindfirstrunclear.md">RtlFindFirstRunClear</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfindlastbackwardrunclear.md">RtlFindLastBackwardRunClear</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfindlongestrunclear.md">RtlFindLongestRunClear</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfindnextforwardrunclear.md">RtlFindNextForwardRunClear</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlAreBitsClear routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

