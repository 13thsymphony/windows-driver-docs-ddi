---
UID: NF.ntddk.RtlIsGenericTableEmptyAvl
title: RtlIsGenericTableEmptyAvl
author: windows-driver-content
description: The RtlIsGenericTableEmptyAvl routine determines if a generic table is empty.
old-location: ifsk\rtlisgenerictableemptyavl.htm
old-project: ifsk
ms.assetid: 9190DA2F-5530-4427-862F-00434DD9C950
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlIsGenericTableEmptyAvl
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
req.alt-api: RtlIsGenericTableEmptyAvl
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
req.irql: <= APC_LEVEL (see Remarks section)
req.iface: 
---

# RtlIsGenericTableEmptyAvl function



## -description
<p>The <b>RtlIsGenericTableEmptyAvl</b> routine determines if a generic table is empty. </p>


## -syntax

````
BOOLEAN RtlIsGenericTableEmptyAvl(
  _In_ PRTL_GENERIC_TABLE Table
);
````


## -parameters
<dl>

### -param Table [in]

<dd>
<p>Pointer to the generic table (<a href="..\ntddk\ns-ntddk--rtl-generic-table.md">RTL_GENERIC_TABLE</a>). The table must have been initialized by calling <b>RtlIsGenericTableEmptyAvl</b>.</p>
</dd>
</dl>

## -returns
<p><b>RtlIsGenericTableEmptyAvl</b> returns <b>FALSE</b> if the table contains one or more elements, <b>TRUE</b> otherwise. </p>

## -remarks
<p>By default, the operating system uses splay trees to implement generic tables, but the <b>RtlIsGenericTableEmptyAvl</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:</p>

<p><code>#define RTL_USE_AVL_TABLES 0</code></p>

<p>If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlIsGenericTableEmptyAvl</b> routine instead of <a href="..\ntddk\nf-ntddk-rtlisgenerictableempty.md">RtlIsGenericTableEmpty</a>. In the call to <b>RtlIsGenericTableEmptyAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk--rtl-avl-table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk--rtl-generic-table.md">RTL_GENERIC_TABLE</a>.</p>

<p>Callers of <b>RtlIsGenericTableEmptyAvl</b> must be running at ≤ APC_LEVEL if the caller-allocated memory at <i>Table</i> is pageable.</p>

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
<p>&lt;= APC_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlIsGenericTableEmptyAvl routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
