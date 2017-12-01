---
UID: NF.ntddk.RtlInsertElementGenericTable
title: RtlInsertElementGenericTable
author: windows-driver-content
description: The RtlInsertElementGenericTable routine adds a new element to a generic table.
old-location: ifsk\rtlinsertelementgenerictable.htm
old-project: ifsk
ms.assetid: 2554a212-edc0-4641-98bb-2db36ff0266f
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RtlInsertElementGenericTable
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
req.alt-api: RtlInsertElementGenericTable
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
req.iface: 
---

# RtlInsertElementGenericTable function



## -description
<p>The <b>RtlInsertElementGenericTable</b> routine adds a new element to a generic table. </p>


## -syntax

````
PVOID RtlInsertElementGenericTable(
  _In_      PRTL_GENERIC_TABLE Table,
  _In_      PVOID              Buffer,
  _In_      CLONG              BufferSize,
  _Out_opt_ PBOOLEAN           NewElement
);
````


## -parameters
<dl>

### -param <i>Table</i> [in]

<dd>
<p>Pointer to the generic table (<a href="..\ntddk\ns-ntddk--rtl-generic-table.md">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>.</p>
</dd>

### -param <i>Buffer</i> [in]

<dd>
<p>Pointer to a caller-allocated buffer containing data to be copied into the new element. For more information, see the description of <a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>. </p>
</dd>

### -param <i>BufferSize</i> [in]

<dd>
<p>Number of bytes to be allocated for caller-supplied data when the new element is inserted. </p>
</dd>

### -param <i>NewElement</i> [out, optional]

<dd>
<p>Pointer to a variable that receives <b>TRUE</b> if a new element with the data at <i>Buffer</i> was inserted in the generic table; or <b>FALSE</b> if the new element was not inserted. </p>
</dd>
</dl>

## -returns
<p><b>RtlInsertElementGenericTable</b> returns a pointer to the newly inserted element's associated data, or it returns a pointer to the existing element's data if a matching element already exists in the generic table. If no matching element is found, but the new element cannot be inserted (for example, because the <i>AllocateRoutine</i> fails), <b>RtlInsertElementGenericTable</b> returns <b>NULL</b>. </p>

## -remarks
<p>To insert an element, <b>RtlInsertElementGenericTable</b> calls the <i>CompareRoutine</i> and <i>AllocateRoutine</i> that were registered when the generic table was initialized by <a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>. After inserting the new element, <b>RtlInsertElementGenericTable</b> rebalances the splay link tree.</p>

<p>When a new element is inserted into the table, its data is copied from <i>Buffer</i> into the new element. Thus the pointer returned by <b>RtlInsertElementGenericTable</b> is never equal to <i>Buffer</i>. </p>

<p>If the caller's <i>CompareRoutine</i> returns <b>GenericEqual</b>, the data at <i>Buffer</i> is assumed to duplicate the data for an existing element in the generic table. In this case, <b>RtlInsertElementGenericTable</b> does not add the new element (and thus does not call the <i>AllocateRoutine</i>), because a generic table cannot have duplicate elements.</p>

<p>If a matching element already exists in the generic table, <b>RtlInsertElementGenericTable</b> returns a pointer to the existing element's data and sets <i>NewElement</i> to <b>FALSE</b>. </p>

<p>Callers of the Rtl..GenericTable routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. </p>

<p>By default, the operating system uses splay trees to implement generic tables. Under some circumstances, operations on a splay tree will make the tree deep and narrow and might even turn it into a straight line. Very deep trees degrade the performance of searches. You can ensure a more balanced, shallower tree implementation of generic tables by using Adelson-Velsky/Landis (AVL) trees. If you want to configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:</p>

<p>#define RTL_USE_AVL_TABLES 0</p>

<p>If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictableavl.md">RtlInsertElementGenericTableAvl</a> routine instead of <b>RtlInsertElementGenericTable</b>. In the call to <b>RtlInsertElementGenericTableAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk--rtl-avl-table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk--rtl-generic-table.md">RTL_GENERIC_TABLE</a>.</p>

<p>Callers of <b>RtlInsertElementGenericTable</b> must be running at IRQL &lt; DISPATCH_LEVEL if either of the following conditions holds:</p>

<p>The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.</p>

<p>The caller-supplied <i>CompareRoutine</i> or <i>AllocateRoutine</i> contains pageable code. </p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h or Ntifs.h)</dt>
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
<p>&lt; DISPATCH_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtldeleteelementgenerictable.md">RtlDeleteElementGenericTable</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInsertElementGenericTable routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
