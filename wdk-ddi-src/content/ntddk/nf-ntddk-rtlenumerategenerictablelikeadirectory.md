---
UID: NF.ntddk.RtlEnumerateGenericTableLikeADirectory
title: RtlEnumerateGenericTableLikeADirectory function
author: windows-driver-content
description: The RtlEnumerateGenericTableLikeADirectory routine returns the elements of a generic table, one-by-one, in collation order.
old-location: ifsk\rtlenumerategenerictablelikeadirectory.htm
old-project: ifsk
ms.assetid: 206c8b70-575d-47e2-a03d-4c88e0d92fe0
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlEnumerateGenericTableLikeADirectory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlEnumerateGenericTableLikeADirectory
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
req.irql: <= APC_LEVEL (See Remarks section)
---

# RtlEnumerateGenericTableLikeADirectory function



## -description
The <b>RtlEnumerateGenericTableLikeADirectory</b> routine returns the elements of a generic table, one-by-one, in collation order.


## -syntax

````
PVOID RtlEnumerateGenericTableLikeADirectory(
  _In_     PRTL_AVL_TABLE          Table,
  _In_opt_ PRTL_AVL_MATCH_FUNCTION MatchFunction,
  _In_opt_ PVOID                   MatchData,
  _In_     ULONG                   NextFlag,
  _Inout_  PVOID                   *RestartKey,
  _Inout_  PULONG                  DeleteCount,
  _In_     PVOID                   Buffer
);
````


## -parameters

### -param Table [in]

A pointer to the Adelson-Velsky/Landis (AVL) table (<a href="ifsk.rtl_avl_table">RTL_AVL_TABLE</a>) that will be enumerated.

### -param MatchFunction [in, optional]

A match function that determines which entries to return. If not specified, all nodes are returned.

### -param MatchData [in, optional]

The data to pass to the match function.

### -param NextFlag [in]

If <i>RestartKey</i> is not <b>NULL</b>, a value of <b>TRUE</b> indicates that the enumeration will skip an element. If <b>FALSE</b> the enumeration resumes where it left off in the previous call to <b>RtlEnumerateGenericTableLikeADirectory</b>. If <i>RestartKey</i> is <b>NULL</b>, a value of <b>TRUE</b> instructs <b>RtlEnumerateGenericTableLikeADirectory</b> to return the next entry in the tree after the entry that matches the data in <i>Buffer</i>. A value of <b>FALSE</b> instructs <b>RtlEnumerateGenericTableLikeADirectory</b> to return the entry in the tree that matches the data in <i>Buffer</i>.

### -param RestartKey [in, out]

A value that determines where to begin or resume the enumeration of generic table elements. If <i>RestartKey</i> is <b>NULL</b>, the enumeration begins or resumes from the position that is described in <i>Buffer</i>. If not <b>NULL</b>, the enumeration resumes from the point that <i>RestartKey</i> indicates. On return, the <i>RestartKey</i> holds a value that indicates the place in the tree where the enumeration left off. On the next call to <b>RtlEnumerateGenericTableLikeADirectory</b> caller should pass the same value back in to inform <b>RtlEnumerateGenericTableLikeADirectory</b> where to resume the enumeration. The following code example illustrates how to do this:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NextFlag = FALSE;
RestartKey = NULL;
DeleteCount = 0;
// Initialize Buffer for start/resume point
Buffer = ...
for (ptr = NULL; ptr != NULL;  ) {
  // Value returned in RestartKey will be passed back in
  // on following call (iteration):
  ptr = RtlEnumerateGenericTableLikeADirectory(
      &amp;MyTable, NULL, NULL, TRUE, &amp;RestartKey,
      &amp;DeleteCount, &amp;Buffer, sizeof(LONG) );
      ...
  // The value output in RestartKey will still be in
  // RestartKey when the
  // RtlEnumerationGenericTableLikeADirectory routine
  // is called in the next iteration of this loop.
  // This ensures that the enumeration will pick up
  // where it left off.
}</pre>
</td>
</tr>
</table></span></div>
If a node is deleted from the tree between calls to <b>RtlEnumerateGenericTableLikeADirectory</b>, enumeration resumes from the position in the tree that is described in <i>Buffer</i>, no matter what the value of <i>RestartKey</i>.

### -param DeleteCount [in, out]

On output, a value that indicates the current count of entries deleted from the table. Caller must pass this value back in on the next call to <b>RtlEnumerateGenericTableLikeADirectory</b>. This value helps the <b>RtlEnumerateGenericTableLikeADirectory</b> routine determine if deletions from the table have occurred between calls to <b>RtlEnumerateGenericTableLikeADirectory</b>. If deletions have occurred, the enumeration resumes with the table entry that matches the data in <i>Buffer</i>, and not with the table entry indicated by <i>RestartKey</i>. If <i>RestartKey</i> is <b>NULL</b>, this parameter has no effect on the enumeration..

### -param Buffer [in]

A key expression that determines where to begin the enumeration, when <i>RestartKey</i> is <b>NULL</b>. Caller can pass in a saved key that matches a particular entry in the table and the enumeration will begin at the entry specified by the saved key, provided <i>RestartKey</i> is <b>NULL</b> and <i>NextFlag</i> is <b>FALSE</b>. To return the key that immediately follows a saved key, pass in the key here, set <i>RestartKey</i> to <b>NULL</b> and <i>NextFlag</i> to <b>TRUE</b>. If the saved key has been deleted, enumeration will begin with the next matched key. 

## -returns
The <b>RtlEnumerateGenericTableLikeADirectory</b> routine returns a pointer to a user-defined structure that is associated with the next table element in the enumeration. If there are no more new elements to return the return value is <b>NULL</b>. 

## -remarks
The <b>RtlEnumerateGenericTableLikeADirectory</b> routine provides a safe means to enumerate a generic table across intermixed insert and delete operations. Starting with the first matched key name, <b>RtlEnumerateGenericTableLikeADirectory</b> returns each name in the table exactly once, unless the name was inserted or deleted during the enumeration. When a key name is inserted or deleted during an enumeration (i.e. between calls to <b>RtlEnumerateGenericTableLikeADirectory</b>) it might or might not be included in the enumeration. Whether such names are included depends on the state of the name when <b>RtlEnumerateGenericTableLikeADirectory</b> processes the directory range in which the name is found.

There are four routines you can use to enumerate a generic table:



The <a href="ifsk.rtlenumerategenerictable">RtlEnumerateGenericTable</a> routine enumerates a generic table in collation order safely across insertions and deletions. However, this routine is not reentrant, so a caller that uses <b>RtlEnumerateGenericTable</b> must acquire exclusive access to the table during the entire enumeration. This routine often used by a caller that is deleting all the elements of a table.

The <a href="ifsk.rtlenumerategenerictablewithoutsplaying">RtlEnumerateGenericTableWithoutSplaying</a>routine enumerates a generic table in collation order, and it is reentrant, so different threads can use it to read the table. However, it is not safe to use <b>RtlEnumerateGenericTableWithoutSplaying</b>across insertions and deletions. Callers that use <b>RtlEnumerateGenericTableWithoutSplaying</b>can share access to the table, but they must lock out changes by other threads during the entire enumeration.

The <a href="ifsk.rtlgetelementgenerictable">RtlGetElementGenericTable</a> routine enumerates a generic table in collation order, and it is reentrant, so different threads can use it to read the table. Furthermore, multiple threads can do insertions and deletions during an enumeration. A thread must obtain shared access for each individual call, but is not required to lock out changes to the table for the entire duration of the enumeration. However, insertions and deletions can cause table entries to be enumerated more than once or dropped completely. For this reason, the <b>RtlGetElementGenericTable</b> routine  is not recommended.

The <b>RtlEnumerateGenericTableLikeADirectory</b> routine enumerates a generic table in collation order; it is reentrant, and it allows multiple threads to do insertions and deletions during the enumeration without dropping or repeating key names in the enumeration. Caller must acquire shared access that locks out changes to the table across each call to the routine, but it is not necessary to hold a lock for the entire duration of the enumeration.

By default, the operating system uses splay trees to implement generic tables, but the <b>RtlEnumerateGenericTableLikeADirectory</b> routine only works with Adelson-Velsky/Landis (AVL) trees. To configure the generic table routines to use AVL trees instead of splay trees in your driver, insert the following define statement in a common header file before including Ntddk.h:

If RTL_USE_AVL_TABLES is not defined, you must use the AVL form of the generic table routines. 

Callers of <b>RtlEnumerateGenericTableLikeADirectory</b> must be running at IRQL &lt;= APC_LEVEL if either of the following conditions holds:

The caller-allocated memory at <i>Table</i> or at <i>Buffer</i> is pageable. 

The caller-supplied <i>MatchFunction</i> contains pageable code. 

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
This routine is available starting with Windows XP.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h, Ntifs.h, or FltKernel.h)</dt>
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
&lt;= APC_LEVEL (See Remarks section)
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rtlenumerategenerictable">RtlEnumerateGenericTable</a>
</dt>
<dt>
<a href="ifsk.rtlenumerategenerictablewithoutsplaying">RtlEnumerateGenericTableWithoutSplaying</a>
</dt>
<dt>
<a href="ifsk.rtlgetelementgenerictable">RtlGetElementGenericTable</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlEnumerateGenericTableLikeADirectory routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
