---
UID: NF.ntddk.RtlLookupElementGenericTable
title: RtlLookupElementGenericTable function
author: windows-driver-content
description: The RtlLookupElementGenericTable routine searches a generic table for an element that matches the specified data.
old-location: ifsk\rtllookupelementgenerictable.htm
old-project: ifsk
ms.assetid: 9182084b-ea11-48e4-acb5-06a8375d05bf
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RtlLookupElementGenericTable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlLookupElementGenericTable
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
req.irql: < DISPATCH_LEVEL (see Remarks section)
---

# RtlLookupElementGenericTable function



## -description
The <b>RtlLookupElementGenericTable</b> routine searches a generic table for an element that matches the specified data. 



## -syntax

````
PVOID RtlLookupElementGenericTable(
  _In_ PRTL_GENERIC_TABLE Table,
  _In_ PVOID              Buffer
);
````


## -parameters

### -param Table [in]

Pointer to the generic table (<a href="ifsk.rtl_generic_table">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <b>RtlInitializeGenericTable</b>.


### -param Buffer [in]

A buffer of search data to pass to the <i>CompareRoutine</i> that was registered when <a href="ifsk.rtlinitializegenerictable">RtlInitializeGenericTable</a> initialized the generic table. For more information, see the description of <b>RtlInitializeGenericTable</b>.


## -returns
<b>RtlLookupElementGenericTable</b> returns a pointer to the caller-supplied data for the desired element in the generic table. It returns <b>NULL</b> if the generic table currently has no elements or if no matching element is found. 


## -remarks
If a matching element is found, <b>RtlLookupElementGenericTable</b> rebalances the generic table's splay tree.

Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. 

By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlLookupElementGenericTableAvl</b> routine instead of <b>RtlLookupElementGenericTable</b>. In the call to <b>RtlLookupElementGenericTableAvl</b>, the caller must pass a <a href="ifsk.rtl_avl_table">RTL_AVL_TABLE</a> table structure rather than <a href="ifsk.rtl_generic_table">RTL_GENERIC_TABLE</a>.

Callers of <b>RtlLookupElementGenericTable</b> must be running at IRQL &lt; DISPATCH_LEVEL if either of the following conditions holds:

The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.

The caller-supplied <i>CompareRoutine</i> contains pageable code. 


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
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
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
&lt; DISPATCH_LEVEL (see Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rtlinitializegenerictable">RtlInitializeGenericTable</a>
</dt>
<dt>
<a href="ifsk.rtlisgenerictableempty">RtlIsGenericTableEmpty</a>
</dt>
<dt>
<a href="ifsk.rtlnumbergenerictableelements">RtlNumberGenericTableElements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlLookupElementGenericTable routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

