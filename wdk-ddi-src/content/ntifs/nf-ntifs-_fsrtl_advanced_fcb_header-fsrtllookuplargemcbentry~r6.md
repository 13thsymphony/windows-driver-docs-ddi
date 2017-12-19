---
UID: NF.ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlLookupLargeMcbEntry~r6
title: FsRtlLookupLargeMcbEntry function
author: windows-driver-content
description: Given a virtual block number (VBN) and a map control block (MCB), the FsRtlLookupLargeMcbEntry routine searches the MCB for mapping information corresponding to the specified VBN.
old-location: ifsk\fsrtllookuplargemcbentry.htm
old-project: ifsk
ms.assetid: 35c6fefb-6045-4b0e-abe8-f78176ca144a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FsRtlLookupLargeMcbEntry
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
req.alt-api: FsRtlLookupLargeMcbEntry
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
req.irql: <= APC_LEVEL
---

# FsRtlLookupLargeMcbEntry function



## -description
Given a virtual block number (VBN) and a map control block (MCB), the <b>FsRtlLookupLargeMcbEntry</b> routine searches the MCB for mapping information corresponding to the specified VBN.



## -syntax

````
BOOLEAN FsRtlLookupLargeMcbEntry(
  _In_      PLARGE_MCB OpaqueMcb,
  _In_      LONGLONG   LargeVbn,
  _Out_opt_ PLONGLONG  LargeLbn,
  _Out_opt_ PLONGLONG  LargeSectorCount,
  _Out_opt_ PLONGLONG  LargeStartingLbn,
  _Out_opt_ PLONGLONG  LargeCountFromStartingLbn,
  _Out_opt_ PULONG     Index
);
````


## -parameters

### -param OpaqueMcb [in]

Pointer to an initialized MCB structure. 


### -param LargeVbn [in]

Pointer to the requested VBN.


### -param LargeLbn [out, optional]

Pointer to a variable that receives the LBN that is mapped to <i>LargeVbn</i> in the mapping entry, or -1 if no such LBN exists. This parameter is optional and can be <b>NULL</b>. 


### -param LargeSectorCount [out, optional]

Pointer to a variable that receives the number of sectors that follow <i>LargeVbn</i> in the mapping run. This parameter is optional and can be <b>NULL</b>. 


### -param LargeStartingLbn [out, optional]

Pointer to a variable that receives the LBN corresponding to the start of the mapping run, or -1 if no such LBN exists. This parameter is optional and can be <b>NULL</b>. 


### -param LargeCountFromStartingLbn [out, optional]

Pointer to a variable that receives the number of sectors in the mapping run. This parameter is optional and can be <b>NULL</b>. 


### -param Index [out, optional]

Pointer to a variable that receives the index of the mapping run that contains the VBN. This parameter is optional and can be <b>NULL</b>. 


## -returns
<b>FsRtlLookupLargeMcbEntry</b> returns <b>TRUE</b> if the specified VBN is within the range of VBNs that are mapped by the MCB, <b>FALSE</b> otherwise. 


## -remarks
<b>FsRtlLookupLargeMcbEntry</b> searches for a mapping entry in the MCB whose run includes the specified VBN. 

If such a mapping exists, the lookup operation yields positive values for the corresponding LBN and sector count, and <b>FsRtlLookupLargeMcbEntry</b> returns <b>TRUE</b>. 

If no such mapping exists, but the specified VBN is lower than the highest VBN mapped by the MCB, this is referred to as a hole in the mapping. In this case, <b>FsRtlLookupLargeMcbEntry</b> still returns <b>TRUE</b>, but the lookup operation yields a value of -1 for the LBN.

If the specified VBN is higher than the highest VBN mapped by the MCB, or if the MCB contains no mappings, <b>FsRtlLookupLargeMcbEntry</b> returns <b>FALSE</b>.


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
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fsrtladdlargemcbentry">FsRtlAddLargeMcbEntry</a>
</dt>
<dt>
<a href="ifsk.fsrtlgetnextlargemcbentry">FsRtlGetNextLargeMcbEntry</a>
</dt>
<dt>
<a href="ifsk.fsrtlinitializelargemcb">FsRtlInitializeLargeMcb</a>
</dt>
<dt>
<a href="ifsk.fsrtllookuplastlargemcbentry">FsRtlLookupLastLargeMcbEntry</a>
</dt>
<dt>
<a href="ifsk.fsrtllookuplastlargemcbentryandindex">FsRtlLookupLastLargeMcbEntryAndIndex</a>
</dt>
<dt>
<a href="ifsk.fsrtlnumberofrunsinlargemcb">FsRtlNumberOfRunsInLargeMcb</a>
</dt>
<dt>
<a href="ifsk.fsrtlremovelargemcbentry">FsRtlRemoveLargeMcbEntry</a>
</dt>
<dt>
<a href="ifsk.fsrtlsplitlargemcb">FsRtlSplitLargeMcb</a>
</dt>
<dt>
<a href="ifsk.fsrtltruncatelargemcb">FsRtlTruncateLargeMcb</a>
</dt>
<dt>
<a href="ifsk.fsrtluninitializelargemcb">FsRtlUninitializeLargeMcb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlLookupLargeMcbEntry routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

