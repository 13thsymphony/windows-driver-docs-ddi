---
UID: NF.wdm.RemoveTailList
title: RemoveTailList function
author: windows-driver-content
description: The RemoveTailList routine removes an entry from the end of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\removetaillist.htm
old-project: kernel
ms.assetid: 67942bf7-28f6-4b2d-a880-9439afaf0bb2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RemoveTailList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RemoveTailList
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
req.product: Windows 10 or later.
---

# RemoveTailList function



## -description
The <b>RemoveTailList</b> routine removes an entry from the end of a doubly linked list of <a href="kernel.list_entry">LIST_ENTRY</a> structures.



## -syntax

````
PLIST_ENTRY RemoveTailList(
  _Inout_ PLIST_ENTRY ListHead
);
````


## -parameters

### -param ListHead [in, out]

Pointer to the <a href="kernel.list_entry">LIST_ENTRY</a> structure that serves as the list header.


## -returns
<b>RemoveTailList</b> returns a pointer to the entry that was at the tail of the list. If the list is empty, <b>RemoveTailList</b> returns <i>ListHead</i>. 


## -remarks
<b>RemoveTailList</b> removes the last entry from the list by setting <i>ListHead</i>-&gt;<b>Blink</b> to point to the second-to-last entry in the list. The routine sets the <b>Flink</b> member of the new first entry to <i>ListHead</i>. In the event the list is empty, this is effectively a no-op.

For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>InsertHeadList</b> can be running at any IRQL. If <b>InsertHeadList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.


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
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any level (See Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.initializelisthead">InitializeListHead</a>
</dt>
<dt>
<a href="kernel.islistempty">IsListEmpty</a>
</dt>
<dt>
<a href="kernel.removeheadlist">RemoveHeadList</a>
</dt>
<dt>
<a href="kernel.removeentrylist">RemoveEntryList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RemoveTailList routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

