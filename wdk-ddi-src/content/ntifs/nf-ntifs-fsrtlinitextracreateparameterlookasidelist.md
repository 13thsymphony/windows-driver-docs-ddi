---
UID: NF.ntifs.FsRtlInitExtraCreateParameterLookasideList
title: FsRtlInitExtraCreateParameterLookasideList function
author: windows-driver-content
description: The FsRtlInitExtraCreateParameterLookasideList routine initializes a paged or nonpaged pool lookaside list used for the allocation of one or more extra create parameter context structures (ECPs) of fixed size.
old-location: ifsk\fsrtlinitextracreateparameterlookasidelist.htm
old-project: ifsk
ms.assetid: 30ad87de-a371-415b-b77f-513369fed098
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlInitExtraCreateParameterLookasideList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlInitExtraCreateParameterLookasideList routine is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlInitExtraCreateParameterLookasideList
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

# FsRtlInitExtraCreateParameterLookasideList function



## -description
The <b>FsRtlInitExtraCreateParameterLookasideList</b> routine initializes a paged or nonpaged pool lookaside list used for the allocation of one or more extra create parameter context structures (ECPs) of fixed size.


## -syntax

````
VOID FsRtlInitExtraCreateParameterLookasideList(
  _Inout_ PVOID                     Lookaside,
  _In_    FSRTL_ECP_LOOKASIDE_FLAGS Flags,
  _In_    SIZE_T                    Size,
  _In_    ULONG                     Tag
);
````


## -parameters

### -param Lookaside [in, out]

Pointer to an opaque <a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a> lookaside list-head structure. For a paged or nonpaged lookaside list, the list-head structure must be allocated from nonpaged pool. 

### -param Flags [in]

Defines pool allocation options. If the <i>Flags</i> parameter contains the FSRTL_ECP_LOOKASIDE_FLAG_NONPAGED_POOL bit flag value, <b>FsRtlInitExtraCreateParameterLookasideList</b> initializes a lookaside list for nonpaged ECP entries of the specified size. Otherwise, <b>FsRtlInitExtraCreateParameterLookasideList</b> initializes a lookaside list for paged ECP entries of the specified size. 

### -param Size [in]

Specifies the size, in bytes, for all ECP entries in the lookaside list. 

### -param Tag [in]

Specifies the pool tag to use when allocating lookaside list ECP entries. For more information about pool tags, see the <i>Tag</i> parameter of <a href="kernel.exallocatepoolwithtag">ExAllocatePoolWithTag</a>. 

## -returns
None

## -remarks
Use this routine to initialize a paged or nonpaged pool lookaside list. Use the <a href="ifsk.fsrtlallocateextracreateparameterfromlookasidelist">FsRtlAllocateExtraCreateParameterFromLookasideList</a> routine to allocate an ECP from the lookaside list, and the <a href="ifsk.fsrtlfreeextracreateparameter">FsRtlFreeExtraCreateParameter</a> routine to return an ECP buffer to the lookaside list for recycling.

Use the <a href="ifsk.fsrtldeleteextracreateparameterlookasidelist">FsRtlDeleteExtraCreateParameterLookasideList</a> routine to free the lookaside list itself.

Drivers must free all ECPs and lookaside lists that they create before they unload.

For more information on using lookaside lists with drivers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565416">Using Lookaside Lists</a>.

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
The FsRtlInitExtraCreateParameterLookasideList routine is available starting with Windows Vista. 
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
<a href="ifsk.ecp_list">ECP_LIST</a>
</dt>
<dt>
<a href="kernel.exallocatepoolwithtag">ExAllocatePoolWithTag</a>
</dt>
<dt>
<a href="ifsk.fsrtlallocateextracreateparameterfromlookasidelist">FsRtlAllocateExtraCreateParameterFromLookasideList</a>
</dt>
<dt>
<a href="ifsk.fsrtldeleteextracreateparameterlookasidelist">FsRtlDeleteExtraCreateParameterLookasideList</a>
</dt>
<dt>
<a href="ifsk.fsrtlfreeextracreateparameter">FsRtlFreeExtraCreateParameter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558775">PAGED_LOOKASIDE_LIST</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInitExtraCreateParameterLookasideList routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
