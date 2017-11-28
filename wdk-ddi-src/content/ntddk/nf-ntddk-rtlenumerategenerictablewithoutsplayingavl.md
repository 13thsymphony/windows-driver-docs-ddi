---
UID: NF.ntddk.RtlEnumerateGenericTableWithoutSplayingAvl
title: RtlEnumerateGenericTableWithoutSplayingAvl
author: windows-driver-content
description: The RtlEnumerateGenericTableWithoutSplayingAvl routine is used to enumerate the elements in a generic table.
old-location: ifsk\rtlenumerategenerictablewithoutsplayingavl.htm
old-project: ifsk
ms.assetid: 27F0C336-3C8C-49B5-A7DB-F0640526CAE8
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: RtlEnumerateGenericTableWithoutSplayingAvl
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
req.alt-api: RtlEnumerateGenericTableWithoutSplayingAvl
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
req.irql: See Remarks section.
req.iface: 
---

# RtlEnumerateGenericTableWithoutSplayingAvl function



## -description
<p>The <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> routine is used to enumerate the elements in a generic table. </p>


## -syntax

````
PVOID RtlEnumerateGenericTableWithoutSplayingAvl(
  _In_    PRTL_GENERIC_TABLE Table,
  _Inout_ PVOID              *RestartKey
);
````


## -parameters
<dl>

### -param <i>Table</i> [in]

<dd>
<p>A pointer to the generic table (<a href="https://msdn.microsoft.com/library/windows/hardware/ff553327">RTL_AVL_TABLE</a>). The table must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh406465">RtlInitializeGenericTableAvl</a>.</p>
</dd>

### -param <i>RestartKey</i> [in, out]

<dd>
<p>An address of the element returned by the previous call to <b>RtlEnumerateGenericTableWithoutSplayingAvl</b>. Should be set to <b>NULL</b> if the enumeration is to start at the first element in the table. </p>
<p>To enumerate all elements in the table, use <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>RestartKey = NULL;
for (ptr = RtlEnumerateGenericTableWithoutSplayingAvl(Table, &amp;RestartKey);
     ptr != NULL;
     ptr = RtlEnumerateGenericTableWithoutSplayingAvl(Table, &amp;RestartKey)) {
        // Process the element pointed to by ptr
}</pre>
</td>
</tr>
</table></span></div>
</dd>
</dl>

## -returns
<p><b>RtlEnumerateGenericTableWithoutSplayingAvl</b> returns a pointer to the caller-defined structure associated with the element. It returns <b>NULL</b> if <i>RestartKey</i> is <b>NULL</b> and the table has no elements or if <i>RestartKey</i> is a returned pointer and there is no next element. </p>

## -remarks
<p>The <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> routine does not actually work with a splay tree but provides an analogous named routine to <b>RtlEnumerateGenericTableWithoutSplayingAvl</b>.</p>

<p><b>RtlEnumerateGenericTableWithoutSplayingAvl</b> can be called repeatedly to process the caller's data in each element of a generic table. </p>

<p>By default, the operating system uses splay trees to implement generic tables, but the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553092">RtlLookupElementGenericTableFullAvl</a> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:</p>

<p>#define RTL_USE_AVL_TABLES 0</p>

<p>If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> routine instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552247">RtlEnumerateGenericTableWithoutSplaying</a>. In the call to <b>RtlEnumerateGenericTableWithoutSplayingAvl</b>, the caller must pass a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553327">RTL_AVL_TABLE</a> table structure rather than <a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>.</p>

<p>Callers of the<i> Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose.</p>

<p>Callers of <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> must be running at IRQL &lt; DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable. </p>

<p>The <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> routine does not actually work with a splay tree but provides an analogous named routine to <b>RtlEnumerateGenericTableWithoutSplayingAvl</b>.</p>

<p><b>RtlEnumerateGenericTableWithoutSplayingAvl</b> can be called repeatedly to process the caller's data in each element of a generic table. </p>

<p>By default, the operating system uses splay trees to implement generic tables, but the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553092">RtlLookupElementGenericTableFullAvl</a> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:</p>

<p>#define RTL_USE_AVL_TABLES 0</p>

<p>If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> routine instead of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552247">RtlEnumerateGenericTableWithoutSplaying</a>. In the call to <b>RtlEnumerateGenericTableWithoutSplayingAvl</b>, the caller must pass a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553327">RTL_AVL_TABLE</a> table structure rather than <a href="https://msdn.microsoft.com/library/windows/hardware/ff553345">RTL_GENERIC_TABLE</a>.</p>

<p>Callers of the<i> Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose.</p>

<p>Callers of <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> must be running at IRQL &lt; DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable. </p>

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
<p>See Remarks section.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406458">RtlEnumerateGenericTableAvl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406465">RtlInitializeGenericTableAvl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406472">RtlIsGenericTableEmptyAvl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406522">RtlNumberGenericTableElementsAvl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlEnumerateGenericTableWithoutSplayingAvl routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
