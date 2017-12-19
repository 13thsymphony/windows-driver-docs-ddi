---
UID: NF.wdm.RtlFindFirstRunClear
title: RtlFindFirstRunClear function
author: windows-driver-content
description: The RtlFindFirstRunClear routine searches for the initial contiguous range of clear bits within a given bitmap.
old-location: kernel\rtlfindfirstrunclear.htm
old-project: kernel
ms.assetid: 21e7e65c-b549-4997-b6dd-a95577edaa26
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlFindFirstRunClear
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
req.product: Windows 10 or later.
---

# RtlFindFirstRunClear function



## -description
The <b>RtlFindFirstRunClear</b> routine searches for the initial contiguous range of clear bits within a given bitmap. 



## -syntax

````
ULONG RtlFindFirstRunClear(
  _In_  PRTL_BITMAP BitMapHeader,
  _Out_ PULONG      StartingIndex
);
````


## -parameters

### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="kernel.rtlinitializebitmap">RtlInitializeBitMap</a> routine. 


### -param StartingIndex [out]

Pointer to a variable in which the starting index of the initial clear run in the bitmap is returned. This is a zero-based value indicating the bit position of the first clear bit in the returned range. Its value is meaningless if <b>RtlFindFirstRunClear</b> cannot find a run of clear bits. 


## -returns
<b>RtlFindFirstRunClear</b> returns either the number of bits in the run beginning at <i>StartingIndex</i>, or zero if it cannot find a run of clear bits within the bitmap. 


## -remarks
A returned run can have a single clear bit. That is, once a clear bit is found, <b>RtlFindFirstRunClear</b> continues searching until it finds the next set bit, and then returns the number of clear bits in the run it found.

Callers of <b>RtlFindFirstRunClear</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlFindFirstRunClear</b> can be called at any IRQL.


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
<a href="kernel.rtlarebitsclear">RtlAreBitsClear</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>
</dt>
<dt>
<a href="kernel.rtlfindclearbits">RtlFindClearBits</a>
</dt>
<dt>
<a href="kernel.rtlfindclearruns">RtlFindClearRuns</a>
</dt>
<dt>
<a href="kernel.rtlfindfirstrunclear">RtlFindFirstRunClear</a>
</dt>
<dt>
<a href="kernel.rtlfindlastbackwardrunclear">RtlFindLastBackwardRunClear</a>
</dt>
<dt>
<a href="kernel.rtlfindlongestrunclear">RtlFindLongestRunClear</a>
</dt>
<dt>
<a href="kernel.rtlfindnextforwardrunclear">RtlFindNextForwardRunClear</a>
</dt>
<dt>
<a href="kernel.rtlsetbits">RtlSetBits</a>
</dt>
<dt>
<a href="kernel.rtlinitializebitmap">RtlInitializeBitMap</a>
</dt>
<dt>
<a href="kernel.rtlnumberofclearbits">RtlNumberOfClearBits</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlFindFirstRunClear routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
