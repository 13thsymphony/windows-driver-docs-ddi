---
UID: NF.wdm.AppendTailList~r1
title: AppendTailList
author: windows-driver-content
description: The AppendTailList routine appends a doubly linked list of LIST_ENTRY structures to the tail of another doubly linked list of LIST_ENTRY structures.
old-location: kernel\appendtaillist.htm
old-project: kernel
ms.assetid: A7C7FBE5-9046-48C7-AEE6-85C17CDE83AD
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: AppendTailList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AppendTailList
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level (See Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# AppendTailList function



## -description
<p>The <b>AppendTailList</b> routine appends a doubly linked list of <a href="kernel.list_entry">LIST_ENTRY</a> structures to the tail of another doubly linked list of <b>LIST_ENTRY</b> structures.</p>


## -syntax

````
VOID AppendTailList(
  _Inout_ PLIST_ENTRY ListHead,
  _Inout_ PLIST_ENTRY ListToAppend
);
````


## -parameters
<dl>

### -param <i>ListHead</i> [in, out]

<dd>
<p>A pointer to the head of the list to which the list pointed to by <i>ListToAppend</i> is to be appended. This parameter must be a valid, non-NULL pointer to the <a href="kernel.list_entry">LIST_ENTRY</a> structure that is the head of a list. This list can be empty.</p>
</dd>

### -param <i>ListToAppend</i> [in, out]

<dd>
<p>A pointer to the first entry in the list to append to the list pointed to by <i>ListHead</i>. This parameter must be a valid, non-NULL pointer to the <a href="kernel.list_entry">LIST_ENTRY</a> structure that is the first entry in a headless list. For more information, see Remarks.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>This routine constructs a list that contains all the combined entries from the input <i>ListHead</i> and <i>ListToAppend</i> lists. When the routine returns, the <a href="kernel.list_entry">LIST_ENTRY</a> structure pointed to by the <i>ListHead</i> parameter is the head of the resulting combined list. The <b>LIST_ENTRY</b> structure pointed to by the <i>ListToAppend</i> parameter is an entry in the resulting combined list.</p>

<p>The caller sets the <i>ListToAppend</i> parameter to point to the first entry in the list to be appended. In this regard, <i>AppendTailList</i> does not conform to the convention followed by the other doubly linked list routines that use the <b>LIST_ENTRY</b> structure. In these other routines, a parameter that represents a list points to the list head instead of to the first entry in the list. If your driver code uses a list head to represent the list to be appended, the list head must be removed from this list before the list is passed as the <i>ListToAppend</i> parameter to <b>AppendTailList</b>. For a code example that shows how to remove this list head, see Examples.</p>

<p><b>AppendTailList</b> can be used to insert a single entry at the tail of a list, but the <b>Flink</b> and <b>Blink</b> members of the <b>LIST_ENTRY</b> structure pointed to by <i>ListToAppend</i> must first be initialized—typically, by calling the <a href="..\wdm\nf-wdm-initializelisthead.md">InitializeListHead</a> routine. In contrast, the <a href="..\wdm\nf-wdm-inserttaillist.md">InsertTailList</a> routine does not require the <b>Flink</b> and <b>Blink</b> members of the <b>LIST_ENTRY</b> structure pointed to by the <i>Entry</i> parameter to be initialized before the <b>InsertTailList</b> call. For this reason, <b>InsertTailList</b> might be more convenient to use to insert a single entry at the tail of a list.</p>

<p>A driver can access the <b>Flink</b> and <b>Blink</b> members of a <b>LIST_ENTRY</b>, but the members must only be updated by the system routines supplied for this purpose.</p>

<p>For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.</p>

<p>Callers of <b>AppendTailList</b> can be running at any IRQL. If <b>AppendTailList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for the list entries must be memory-resident.</p>

<p>The following code example shows how to write a function named <code>MyAppendTailList</code> that is similar to <b>AppendTailList</b>, but that treats the <i>ListToAppend</i> parameter as a pointer to a list head instead of as a pointer to the first entry in a (headless) list. Unlike <b>AppendTailList</b>, the <code>MyAppendTailList</code> function avoids including the <b>LIST_ENTRY</b> structure pointed to by the <i>ListToAppend</i> parameter in the entries that are appended to the list pointed to by the <i>ListHead</i> parameter.</p>

<p>The <code>MyAppendTailList</code> function in this code example treats both the <i>ListHead</i> and <i>ListToAppend</i> parameters as pointers to list heads. When this function returns, the list pointed to by <i>ListToAppend</i> is empty; that is, it consists of a list head that has no associated list entries. All of the entries that were initially in this list have been appended to the list pointed to by <i>ListHead</i>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows Vista.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level (See Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-initializelisthead.md">InitializeListHead</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-inserttaillist.md">InsertTailList</a>
</dt>
<dt>
<a href="kernel.list_entry">LIST_ENTRY</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-removeentrylist.md">RemoveEntryList</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20AppendTailList routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
