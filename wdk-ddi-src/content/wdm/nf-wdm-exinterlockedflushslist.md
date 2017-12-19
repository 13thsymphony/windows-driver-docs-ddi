---
UID: NF.wdm.ExInterlockedFlushSList
title: ExInterlockedFlushSList function
author: windows-driver-content
description: The ExInterlockedFlushSList routine atomically removes all entries from a sequenced singly linked list.
old-location: kernel\exinterlockedflushslist.htm
old-project: kernel
ms.assetid: 98fcada7-5160-4eb2-ac7c-0ab1192340a9
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ExInterlockedFlushSList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExInterlockedFlushSList
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
req.irql: Any level (see Remarks section)
req.product: Windows 10 or later.
---

# ExInterlockedFlushSList function



## -description
The <b>ExInterlockedFlushSList</b> routine atomically removes all entries from a sequenced singly linked list.



## -syntax

````
PSLIST_ENTRY ExInterlockedFlushSList(
  _Inout_ PSLIST_HEADER ListHead
);
````


## -parameters

### -param ListHead [in, out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list.


## -returns
If there were entries on the specified list, <b>ExInterlockedFlushSList</b> returns a pointer to the first <a href="kernel.slist_entry">SLIST_ENTRY</a> structure that was entry on the list; otherwise, it returns <b>NULL</b>.


## -remarks
<b>ExInterlockedFlushSList</b> does not delete the <a href="kernel.slist_entry">SLIST_ENTRY</a> structures that made up the list; it only sets the internal pointer of <i>ListHead</i> to the beginning of the list to <b>NULL</b>. The driver must free the entries explicitly.

The routine returns a pointer to the first <b>SLIST_ENTRY</b> structure that was on the list. The driver can use this pointer to iterate through the entries.

For more information about using this routine to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>ExInterlockedFlushSList</b> can be running at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.


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
Any level (see Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.exinitializeslisthead">ExInitializeSListHead</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInterlockedFlushSList routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

