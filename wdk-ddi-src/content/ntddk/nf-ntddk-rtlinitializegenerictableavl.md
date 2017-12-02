---
UID: NF.ntddk.RtlInitializeGenericTableAvl
title: RtlInitializeGenericTableAvl
author: windows-driver-content
description: The RtlInitializeGenericTableAvl routine initializes a generic table using Adelson-Velsky/Landis (AVL) trees.
old-location: ifsk\rtlinitializegenerictableavl.htm
old-project: ifsk
ms.assetid: D89713A8-7CE7-4A87-AED7-62ACF7D1BA06
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlInitializeGenericTableAvl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlInitializeGenericTableAvl
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.iface: 
---

# RtlInitializeGenericTableAvl function



## -description
<p>The <b>RtlInitializeGenericTableAvl</b> routine initializes a generic table using Adelson-Velsky/Landis (AVL) trees.</p>


## -syntax

````
VOID RtlInitializeGenericTableAvl(
  _Out_    PRTL_AVL_TABLE            Table,
  _In_     PRTL_AVL_COMPARE_ROUTINE  CompareRoutine,
  _In_     PRTL_AVL_ALLOCATE_ROUTINE AllocateRoutine,
  _In_     PRTL_AVL_FREE_ROUTINE     FreeRoutine,
  _In_opt_ PVOID                     TableContext
);
````


## -parameters
<dl>

### -param Table [out]

<dd>
<p>A pointer to a caller-allocated buffer, which must be at least <b>sizeof</b>(<a href="..\ntddk\ns-ntddk--rtl-avl-table.md">RTL_AVL_TABLE</a>) bytes in size, to contain the initialized generic table structure. </p>
</dd>

### -param CompareRoutine [in]

<dd>
<p>An entry point of a comparison callback routine, declared as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>RTL_GENERIC_COMPARE_RESULTS
(*PRTL_AVL_COMPARE_ROUTINE) (
    __in struct _RTL_AVL_TABLE  *Table,
    __in PVOID  FirstStruct,
    __in PVOID  SecondStruct
    ); </pre>
</td>
</tr>
</table></span></div>
<p>The <i>CompareRoutine</i> parameters are as follows:</p>
<p></p>
<dl>

### -param Table

<dd>
<p>A pointer to the generic table.</p>
</dd>

### -param FirstStruct

<dd>
<p>A pointer to the first item to be compared.</p>
</dd>

### -param SecondStruct

<dd>
<p>A pointer to the second item to be compared.</p>
</dd>
</dl>
<p>The <i>CompareRoutine</i> must strictly track the ordering of all elements in the generic table so that it can identify any particular element. The caller-defined structure for element data usually includes a member whose value is unique and can be used as a sorting key. All <i>Rtl...GenericTableAvl</i> routines that call the <i>CompareRoutine</i> take a buffer pointer as a parameter, which is passed in turn to the <i>CompareRoutine</i>. The buffer contains a caller-supplied key value to be matched by the <i>CompareRoutine</i> to the key of the element that is being searched for. </p>
<p>Given two such key values, the <i>CompareRoutine</i> returns <b>GenericLessThan</b>, <b>GenericGreaterThan</b>, or <b>GenericEqual</b>. </p>
</dd>

### -param AllocateRoutine [in]

<dd>
<p>An entry point of an allocation callback routine, declared as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PVOID
(*PRTL_AVL_ALLOCATE_ROUTINE) (
    __in struct _RTL_AVL_TABLE  *Table,
    __in CLONG  ByteSize
    );</pre>
</td>
</tr>
</table></span></div>
<p>The <i>AllocateRoutine</i> parameters are as follows:</p>
<p></p>
<dl>

### -param Table

<dd>
<p>A pointer to the generic table.</p>
</dd>

### -param ByteSize

<dd>
<p>The number of bytes to allocate.</p>
</dd>
</dl>
<p>For each new element, the <i>AllocateRoutine</i> is called to allocate memory for caller-supplied data plus some additional memory for use by the <i>Rtl...GenericTableAvl</i> routines. Note that because of this "additional memory," caller-supplied routines must not access the first <b>sizeof</b>(RTL_BALANCED_LINKS) bytes of any element in the generic table. </p>
</dd>

### -param FreeRoutine [in]

<dd>
<p>An entry point of a deallocation callback routine, declared as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
(*PRTL_AVL_FREE_ROUTINE) (
    __in struct _RTL_AVL_TABLE  *Table,
    __in PVOID  Buffer
    );</pre>
</td>
</tr>
</table></span></div>
<p>The <i>FreeRoutine</i> parameters are as follows:</p>
<p></p>
<dl>

### -param Table

<dd>
<p>A pointer to the generic table.</p>
</dd>

### -param Buffer

<dd>
<p>A pointer to the element that is being deleted.</p>
</dd>
</dl>
<p><i>Rtl...GenericTableAvl</i> routines call the <i>FreeRoutine</i> to deallocate memory for elements to be deleted from the generic table. The <i>FreeRoutine</i> is the opposite of the <i>AllocateRoutine</i>. </p>
</dd>

### -param TableContext [in, optional]

<dd>
<p>An optional pointer to a caller-supplied context for the generic table. This parameter can be <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>File systems call <b>RtlInitializeGenericTableAvl</b> to initialize a generic table to store file system-specific data, such as name-lookup information for currently open files. The sort order, structure, and contents of the elements are caller-defined. </p>

<p>File systems must call <b>RtlInitializeGenericTableAvl</b> to initialize the generic table before they use any other <i>Rtl...GenericTableAvl</i> routines on the new generic table. The initialized generic table structure should be considered opaque.</p>

<p>Callers of the <i>Rtl...GenericTableAvl</i> routines are responsible for exclusively synchronizing access to the generic table. An exclusive fast mutex is the most efficient synchronization mechanism to use for this purpose. </p>

<p>The caller-supplied <i>CompareRoutine</i> is called before the <i>AllocateRoutine</i> to locate an appropriate location at which a new element should be inserted. The <i>CompareRoutine</i> also is called before the <i>FreeRoutine</i> to locate an element to be deleted.</p>

<p>The <b>RtlInitializeGenericTableAvl</b> routine explicitlly allocates a generic table that uses AVL trees. Use of this routine and the other <i>Rtl...GenericTableAvl</i> routines is necessary when AVL tree based tables are desired and RTL_USE_AVL_TABLES is not define before including <i>Ntddk.h</i>.</p>

<p> If you want to configure the generic table routines, <i>Rtl...GenericTable</i>, to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including <i>Ntddk.h</i>:</p>

<p>Callers of <b>RtlInitializeGenericTableAvl</b> must be running at IRQL &lt;= DISPATCH_LEVEL. Note that if <i>Rtl...GenericTableAvl</i> routines are to be used at IRQL DISPATCH_LEVEL, the <i>CompareRoutine</i>, <i>AllocateRoutine</i>, and <i>FreeRoutine</i> must all be nonpageable code, and the <i>AllocateRoutine</i> should allocate memory from nonpaged pool.</p>

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
<p>Available in Windows XP and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h, Ntifs.h, or Fltkernel.h)</dt>
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
<p>&lt;= DISPATCH_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exinitializefastmutex.md">ExInitializeFastMutex</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtldeleteelementgenerictableavl.md">RtlDeleteElementGenericTableAvl</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlenumerategenerictableavl.md">RtlEnumerateGenericTableAvl</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlgetelementgenerictable.md">RtlGetElementGenericTableAvl</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinitializegenerictable.md">RtlInitializeGenericTable</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertelementgenerictableavl.md">RtlInsertElementGenericTableAvl</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtllookupelementgenerictableavl.md">RtlLookupElementGenericTableAvl</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlnumbergenerictableelementsavl.md">RtlNumberGenericTableElementsAvl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInitializeGenericTableAvl routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
