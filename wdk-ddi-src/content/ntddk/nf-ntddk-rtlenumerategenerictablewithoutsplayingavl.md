---
UID: NF:ntddk.RtlEnumerateGenericTableWithoutSplayingAvl
title: RtlEnumerateGenericTableWithoutSplayingAvl function
author: windows-driver-content
description: The RtlEnumerateGenericTableWithoutSplayingAvl routine is used to enumerate the elements in a generic table.
old-location: ifsk\rtlenumerategenerictablewithoutsplayingavl.htm
old-project: ifsk
ms.assetid: 27F0C336-3C8C-49B5-A7DB-F0640526CAE8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlEnumerateGenericTableWithoutSplayingAvl, RtlEnumerateGenericTableWithoutSplayingAvl routine [Installable File System Drivers], ifsk.rtlenumerategenerictablewithoutsplayingavl, ntddk/RtlEnumerateGenericTableWithoutSplayingAvl
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlEnumerateGenericTableWithoutSplayingAvl
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlEnumerateGenericTableWithoutSplayingAvl function
The <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> routine is used to enumerate the elements in a generic table.

## Syntax

````
PVOID RtlEnumerateGenericTableWithoutSplayingAvl(
  _In_    PRTL_GENERIC_TABLE Table,
  _Inout_ PVOID              *RestartKey
);
````

## Parameters

`Table`

A pointer to the generic table (<a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a>). The table must have been initialized by calling <a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>.

`RestartKey`

An address of the element returned by the previous call to <b>RtlEnumerateGenericTableWithoutSplayingAvl</b>. Should be set to <b>NULL</b> if the enumeration is to start at the first element in the table. 

To enumerate all elements in the table, use <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> as follows:

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


## Return Value

<b>RtlEnumerateGenericTableWithoutSplayingAvl</b> returns a pointer to the caller-defined structure associated with the element. It returns <b>NULL</b> if <i>RestartKey</i> is <b>NULL</b> and the table has no elements or if <i>RestartKey</i> is a returned pointer and there is no next element.

## Remarks

The <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> routine does not actually work with a splay tree but provides an analogous named routine to <b>RtlEnumerateGenericTableWithoutSplayingAvl</b>.

<b>RtlEnumerateGenericTableWithoutSplayingAvl</b> can be called repeatedly to process the caller's data in each element of a generic table. 

By default, the operating system uses splay trees to implement generic tables, but the <a href="..\ntddk\nf-ntddk-rtllookupelementgenerictablefullavl.md">RtlLookupElementGenericTableFullAvl</a> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:

#define RTL_USE_AVL_TABLES 0

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. For example, use the <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> routine instead of <a href="..\ntddk\nf-ntddk-rtlenumerategenerictablewithoutsplaying.md">RtlEnumerateGenericTableWithoutSplaying</a>. In the call to <b>RtlEnumerateGenericTableWithoutSplayingAvl</b>, the caller must pass a <a href="..\ntddk\ns-ntddk-_rtl_avl_table.md">RTL_AVL_TABLE</a> table structure rather than <a href="..\ntddk\ns-ntddk-_rtl_generic_table.md">RTL_GENERIC_TABLE</a>.

Callers of the<i> Rtl..GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose.

Callers of <b>RtlEnumerateGenericTableWithoutSplayingAvl</b> must be running at IRQL &lt; DISPATCH_LEVEL if the caller-allocated memory for the generic table is pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |

## See Also

<a href="..\ntddk\nf-ntddk-rtlisgenerictableemptyavl.md">RtlIsGenericTableEmptyAvl</a>



<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelementsavl.md">RtlNumberGenericTableElementsAvl</a>



<a href="..\ntddk\nf-ntddk-rtlinitializegenerictableavl.md">RtlInitializeGenericTableAvl</a>



<a href="..\ntddk\nf-ntddk-rtlenumerategenerictableavl.md">RtlEnumerateGenericTableAvl</a>