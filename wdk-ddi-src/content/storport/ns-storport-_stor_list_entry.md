---
UID: NS.STORPORT._STOR_LIST_ENTRY
title: _STOR_LIST_ENTRY
author: windows-driver-content
description: A STOR_LIST_ENTRY structure describes an entry in a doubly linked list or serves as the header for such a list.
old-location: storage\stor_list_entry.htm
old-project: storage
ms.assetid: 41E713D9-9499-40EB-8B21-DDB73362BAE3
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _STOR_LIST_ENTRY, STOR_LIST_ENTRY, *PSTOR_LIST_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STOR_LIST_ENTRY
req.alt-loc: storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# _STOR_LIST_ENTRY structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]
A <b>STOR_LIST_ENTRY</b> structure describes an entry in a doubly linked list or serves as the header for such a list.


## -syntax

````
typedef struct _STOR_LIST_ENTRY {
  struct _STOR_LIST_ENTRY  *Flink;
  struct _STOR_LIST_ENTRY  *Blink;
} STOR_LIST_ENTRY, *PSTOR_LIST_ENTRY;
````


## -struct-fields

### -field Flink

For a <b>LIST_ENTRY</b> structure that serves as a list entry, the <b>Flink</b> member points to the next entry in the list or to the list header if there is no next entry in the list. 
For a <b>LIST_ENTRY</b> structure that serves as the list header, the <b>Flink</b> member points to the first entry in the list or to the LIST_ENTRY structure itself if the list is empty.

### -field Blink

For a <b>LIST_ENTRY</b> structure that serves as a list entry, the <b>Blink</b> member points to the previous entry in the list or to the list header if there is no previous entry in the list.
For a <b>LIST_ENTRY</b> structure that serves as the list header, the <b>Blink</b> member points to the last entry in the list or to the <b>LIST_ENTRY</b> structure itself if the list is empty.

## -remarks
A <b>STOR_LIST_ENTRY</b> structure that describes the list head must have been initialized by calling <a href="storage.StorPortInitializeListHead">StorPortInitializeListHead
</a>.

A driver can access the <b>Flink</b> or <b>Blink</b> members of a <b>STOR_LIST_ENTRY</b>, but the members must only be updated by the system routines supplied for this purpose.

For more information about how to use <b>STOR_LIST_ENTRY</b> structures to implement a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.storportinterlockedinsertheadlist">StorPortInterlockedInsertHeadList</a>
</dt>
<dt>
<a href="storage.storportinterlockedinserttaillist">StorPortInterlockedInsertTailList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt790430">StorPortInterlockedRemoveHeadList</a>
</dt>
<dt>
<a href="kernel.initializelisthead">InitializeListHead</a>
</dt>
<dt>
<a href="kernel.insertheadlist">InsertHeadList</a>
</dt>
<dt>
<a href="kernel.inserttaillist">InsertTailList</a>
</dt>
<dt>
<a href="kernel.islistempty">IsListEmpty</a>
</dt>
<dt>
<a href="kernel.removeentrylist">RemoveEntryList</a>
</dt>
<dt>
<a href="kernel.removeheadlist">RemoveHeadList</a>
</dt>
<dt>
<a href="kernel.removetaillist">RemoveTailList</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_LIST_ENTRY structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
