---
UID: NF.wdm.FirstEntrySList
title: FirstEntrySList
author: windows-driver-content
description: The FirstEntrySList routine returns the first entry in a sequenced singly linked list.
old-location: kernel\firstentryslist.htm
old-project: kernel
ms.assetid: 80444a10-91f3-44b5-ad20-3d3d8f49ca60
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: FirstEntrySList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FirstEntrySList
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
req.irql: Any level
req.iface: 
req.product: Windows 10 or later.
---

# FirstEntrySList function



## -description
<p>The <b>FirstEntrySList</b> routine returns the first entry in a sequenced singly linked list.</p>


## -syntax

````
PSLIST_ENTRY FirstEntrySList(
  _In_ PSLIST_HEADER SListHead
);
````


## -parameters
<dl>

### -param <i>SListHead</i> [in]

<dd>
<p>Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list.</p>
</dd>
</dl>

## -returns
<p><b>FirstEntrySList</b> returns a pointer to the first <a href="kernel.slist_entry">SLIST_ENTRY</a> structure on the list. If the list is empty, the routine returns <b>NULL</b>.</p>

## -remarks
<p>Unlike other sequenced singly linked list routines, the <b>FirstEntrySList</b> routine is not atomic. For more information about sequenced singly linked lists, see <a href="kernel.singly_and_doubly_linked_lists#sequenced_singly_linked_lists#sequenced_singly_linked_lists">Sequenced Singly Linked Lists</a>. Callers of this routine can run at any level. If called at IRQL &gt;= DISPATCH_LEVEL, the storage for <b>ListHead</b> must be resident.</p>

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
<dt>Wdm.h (include Wdm.h, Ntifs.h, or Ntddk.h)</dt>
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
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.slist_entry">SLIST_ENTRY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FirstEntrySList routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
