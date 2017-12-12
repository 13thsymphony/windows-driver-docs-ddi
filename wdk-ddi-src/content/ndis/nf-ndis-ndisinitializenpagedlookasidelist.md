---
UID: NF.ndis.NdisInitializeNPagedLookasideList
title: NdisInitializeNPagedLookasideList function
author: windows-driver-content
description: The NdisInitializeNPagedLookasideList function initializes a lookaside list. After a successful initialization, nonpaged fixed-size blocks can be allocated from and freed to the lookaside list.
old-location: netvista\ndisinitializenpagedlookasidelist.htm
old-project: netvista
ms.assetid: d240f2cc-18a6-4c2d-889f-e25a9486d5fe
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisInitializeNPagedLookasideList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisInitializeNPagedLookasideList (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see         NdisInitializeNPagedLookasideList (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisInitializeNPagedLookasideList
req.alt-loc: ndis.h
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL (see Remarks section)
---

# NdisInitializeNPagedLookasideList function



## -description
The 
  <b>NdisInitializeNPagedLookasideList</b> function initializes a lookaside list. After a successful
  initialization, nonpaged fixed-size blocks can be allocated from and freed to the lookaside list.



## -syntax

````
VOID NdisInitializeNPagedLookasideList(
  _In_     PNPAGED_LOOKASIDE_LIST Lookaside,
  _In_opt_ PALLOCATE_FUNCTION     Allocate,
  _In_opt_ PFREE_FUNCTION         Free,
  _In_     ULONG                  Flags,
  _In_     ULONG                  Size,
  _In_     ULONG                  Tag,
  _In_     USHORT                 Depth
);
````


## -parameters

### -param Lookaside [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a> structure that
     contains the caller-supplied lookaside list head to be initialized. The structure must be 16-byte aligned on 64-bit platforms. The driver must provide a list head
     that is resident—that is, in nonpaged system space. 


### -param Allocate [in, optional]

A function entry point that is either <b>NULL</b> or specifies the entry point of a caller-supplied 
     <i>Allocate</i> function that will allocate an entry of the size that is specified in the 
     <i>Size</i> member whenever it is called. If 
     <i>Allocate</i> is <b>NULL</b>, the 
     <a href="netvista.ndisallocatefromnpagedlookasidelist">
     NdisAllocateFromNPagedLookasideList</a> function subsequently allocates entries on behalf of the
     caller. If the caller provides an 
     <i>Allocate</i> function, it also must provide a 
     <i>Free</i> function.


### -param Free [in, optional]

A function entry point that is either <b>NULL</b> or specifies the entry point of a caller-supplied 
     <i>Free</i> function that will free an entry of the size that is specified in the 
     <i>Size</i> member whenever it is called. If 
     <i>Free</i> is <b>NULL</b>, the 
     <a href="netvista.ndisfreetonpagedlookasidelist">
     NdisFreeToNPagedLookasideList</a> function subsequently frees entries on behalf of the caller.


### -param Flags [in]

Must be zero. This parameter is reserved.


### -param Size [in]

The size, in bytes, of each entry to be subsequently allocated from the lookaside list.


### -param Tag [in]

A caller-supplied pool tag for lookaside list entries. The 
     <i>Tag</i> is a string of four characters that is delimited by single quote marks (for example, 'derF').
     The characters are usually specified in reverse order so they are easier to read when dumping pool or
     tracking pool usage in the debugger.


### -param Depth [in]

Must be zero. This parameter is also reserved.


## -returns
None


## -remarks
<b>NdisInitializeNPagedLookasideList</b> initializes the caller-supplied list head but allocates no memory
    for list entries. The initial entries are allocated on an as-needed basis either with calls to the 
    <a href="netvista.ndisallocatefromnpagedlookasidelist">
    NdisAllocateFromNPagedLookasideList</a> function or by the driver-supplied 
    <i>Allocate</i> callback function at the 
    <i>Allocate</i> parameter. The list is populated as the driver frees entries back to the list with the 
    <a href="netvista.ndisfreetonpagedlookasidelist">
    NdisFreeToNPagedLookasideList</a> function. Entries collect on the list until a system-determined but
    dynamically sized limit is reached. Then, any surplus entries in the lookaside list are returned to
    nonpaged pool, either by 
    <b>NdisFreeToNPagedLookasideList</b> or with calls to the driver-supplied 
    <i>Free</i> callback function at the 
    <i>Free</i> parameter.

All entries in the lookaside list are of the same size, which is specified in the 
    <i>Size</i> parameter. A lookaside list is particularly useful to drivers that must dynamically allocate
    and free fixed-size context areas in which to maintain run-time state about their outstanding I/O
    operations. For instance, connection-oriented NDIS drivers are likely to find lookaside lists
    particularly useful because such drivers usually maintain a dynamic set of context areas to track
    outgoing and incoming calls.

It is more efficient for a driver to allow the 
    <a href="netvista.ndisallocatefromnpagedlookasidelist">
    NdisAllocateFromNPagedLookasideList</a> and 
    <a href="netvista.ndisfreetonpagedlookasidelist">
    NdisFreeToNPagedLookasideList</a> functions to manage the allocation and deallocation of entries (see
    the 
    <a href="kernel.exallocatepoolwithtag">ExAllocatePoolWithTag</a> and 
    <a href="kernel.exfreepool">ExFreePool</a> functions). However, a driver that
    tracks state internally about its memory usage might supply 
    <i>Allocate</i> and 
    <i>Free</i> functions to 
    <b>NdisInitializeNPagedLookasideList</b>.

Callers of 
    <b>NdisInitializeNPagedLookasideList</b> must be running at IRQL &lt;= DISPATCH_LEVEL, but are usually
    running at PASSIVE_LEVEL.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/9951064a-f685-4cf6-81ce-ec46a7fe9d0f">
   NdisInitializeNPagedLookasideList (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see
   
   <b>
   NdisInitializeNPagedLookasideList (NDIS 5.1)</b>) in Windows XP.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL (see Remarks section)

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exallocatepoolwithtag">ExAllocatePoolWithTag</a>
</dt>
<dt>
<a href="kernel.exfreepool">ExFreePool</a>
</dt>
<dt>
<a href="netvista.ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndisdeletenpagedlookasidelist">
   NdisDeleteNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndisfreetonpagedlookasidelist">
   NdisFreeToNPagedLookasideList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556431">NPAGED_LOOKASIDE_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisInitializeNPagedLookasideList function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

