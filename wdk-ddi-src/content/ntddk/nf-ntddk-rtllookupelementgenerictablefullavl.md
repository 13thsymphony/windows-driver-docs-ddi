---
UID: NF.ntddk.RtlLookupElementGenericTableFullAvl
title: RtlLookupElementGenericTableFullAvl
author: windows-driver-content
description: The RtlLookupElementGenericTableFullAvl routine searches a generic table for an element that matches the specified data.
old-location: ifsk\rtllookupelementgenerictablefullavl.htm
old-project: ifsk
ms.assetid: fddb2e23-ddb3-48bc-a94e-0ca9a8580b78
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlLookupElementGenericTableFullAvl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlLookupElementGenericTableFullAvl
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

# RtlLookupElementGenericTableFullAvl function



## -description
<p>The <b>RtlLookupElementGenericTableFullAvl</b> routine searches a generic table for an element that matches the specified data.</p>


## -syntax

````
PVOID RtlLookupElementGenericTableFullAvl(
  _In_  PRTL_AVL_TABLE      Table,
  _In_  PVOID               Buffer,
  _Out_ PVOID               *NodeOrParent,
  _Out_ TABLE_SEARCH_RESULT *SearchResult
);
````


## -parameters
<dl>

### -param Table [in]

<dd>
<p>Pointer to the generic Adelson-Velsky/Landis (AVL) table (<a href="..\ntddk\ns-ntddk--rtl-avl-table.md">RTL_AVL_TABLE</a>). The table must have been initialized by calling <a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>.</p>
</dd>

### -param Buffer [in]

<dd>
<p>A buffer of search data to pass to the <i>CompareRoutine</i> that was registered when <a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a> initialized the generic table. For more information, see the description of <b>RtlInitializeGenericTableAvl</b>.</p>
</dd>

### -param NodeOrParent [out]

<dd>
<p>On output, a value that describes the relationship of the <i>NodeOrParent</i> with the table entry (node) that <b>RtlLookupElementGenericTableFullAvl</b> is searching for. The <i>SearchResult</i> parameter can have any of the following values:</p>
<p></p>
<dl>

### -param TableEmptyTree

<dd>
<p>The tree was empty. The contents of <i>NodeOrParent</i> has <i>not</i> been altered.</p>
</dd>

### -param TableFoundNode

<dd>
<p>The <b>RtlLookupElementGenericTableFullAvl</b> routine found a table entry whose key matches the data in <i>Buffer</i>. <i>NodeOrParent</i> contains a pointer to the matched entry.</p>
</dd>

### -param TableInsertAsLeft

<dd>
<p>The <b>RtlLookupElementGenericTableFullAvl</b> routine did <i>not</i>find a table entry whose key matches the data in <i>Buffer</i>. I<i>not</i>f the entry that <b>RtlLookupElementGenericTableFullAvl</b> searched for were in the table, it would be the left child of the entry that <i>NodeOrParent</i> points to.</p>
</dd>

### -param TableInsertAsRight

<dd>
<p>The <b>RtlLookupElementGenericTableFullAvl</b> routine did <i>not</i>find a table entry whose key matches the data in <i>Buffer</i>. If the entry that <b>RtlLookupElementGenericTableFullAvl</b> searched for were in the table, it would be the right child of the entry that <i>NodeOrParent</i> points to.</p>
</dd>
</dl>
</dd>

### -param SearchResult [out]

<dd>
<p>A pointer to a table entry. If the <b>RtlLookupElementGenericTableFullAvl</b> routine matches an entry, <i>NodeOrParent</i>points to the matched entry. If the <b>RtlLookupElementGenericTableFullAvl</b> routine fails to find a match, <i>NodeOrParent</i> points to the entry that would be the parent of the entry that <b>RtlLookupElementGenericTableFullAvl</b> routine was searching for.</p>
</dd>
</dl>

## -returns
<p><b>RtlLookupElementGenericTableFullAvl</b> returns a pointer to the user data that is associated with the matching element in the generic table, or <b>NULL</b> if the generic table currently has no elements or if no matching element is found.</p>

## -remarks
<p>By default, the operating system uses splay trees to implement generic tables, but the <b>RtlLookupElementGenericTableFullAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:</p>

<p>#define RTL_USE_AVL_TABLES 0</p>

<p>If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlLookupElementGenericTableFullAvl</b> routine instead of <a href="..\ntddk\nf-ntddk-rtllookupelementgenerictable.md">RtlLookupElementGenericTable</a>. In the call to <b>RtlLookupElementGenericTableFullAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk--rtl-avl-table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk--rtl-generic-table.md">RTL_GENERIC_TABLE</a>.</p>

<p>Callers of the<i> Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. </p>

<p>Callers of <b>RtlLookupElementGenericTableFullAvl</b> must be running at IRQL &lt; DISPATCH_LEVEL if either of the following conditions holds:</p>

<p>The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable.</p>

<p>The caller-supplied <i>CompareRoutine</i> contains pageable code. </p>

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
<p>Available starting with Windows XP.</p>
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
<a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlisgenerictableemptyavl.md">RtlIsGenericTableEmptyAvl</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelementsavl.md">RtlNumberGenericTableElementsAvl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlLookupElementGenericTableFullAvl routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
