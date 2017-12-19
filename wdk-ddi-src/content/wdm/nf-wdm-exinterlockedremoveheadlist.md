---
UID: NF.wdm.ExInterlockedRemoveHeadList
title: ExInterlockedRemoveHeadList function
author: windows-driver-content
description: The ExInterlockedRemoveHeadList routine removes an entry from the beginning of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\exinterlockedremoveheadlist.htm
old-project: kernel
ms.assetid: d024da2c-9629-4907-98b8-a29dc6022ac0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: ExInterlockedRemoveHeadList
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
req.alt-api: ExInterlockedRemoveHeadList
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

# ExInterlockedRemoveHeadList function



## -description
The <b>ExInterlockedRemoveHeadList</b> routine removes an entry from the beginning of a doubly linked list of <a href="kernel.list_entry">LIST_ENTRY</a> structures. 



## -syntax

````
PLIST_ENTRY ExInterlockedRemoveHeadList(
  _Inout_ PLIST_ENTRY ListHead,
  _Inout_ PKSPIN_LOCK Lock
);
````


## -parameters

### -param ListHead [in, out]

A pointer to the <a href="kernel.list_entry">LIST_ENTRY</a> structure that serves as the list header.


### -param Lock [in, out]

A pointer to a <b>KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="kernel.keinitializespinlock">KeInitializeSpinLock</a>. You must use this spin lock only with the <b>ExInterlocked<i>Xxx</i>List</b> routines.


## -returns
<b>ExInterlockedRemoveHeadList</b> returns a pointer to the <a href="kernel.list_entry">LIST_ENTRY</a> structure removed from the list. If the list was empty, the routine returns <b>NULL</b>.


## -remarks
<b>ExInterlockedRemoveHeadList</b> performs a similar operation as <a href="kernel.removeheadlist">RemoveHeadList</a>, but atomically. Do not mix atomic and non-atomic calls on the same list.

For more information about using this routine to implement a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

The <b>ExInterlockedRemoveHeadList</b> routine can be called at any IRQL. The storage for the <i>ListHead</i> parameter must be resident at all IRQLs.


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
<a href="kernel.exinterlockedinsertheadlist">ExInterlockedInsertHeadList</a>
</dt>
<dt>
<a href="kernel.exinterlockedinserttaillist">ExInterlockedInsertTailList</a>
</dt>
<dt>
<a href="kernel.initializelisthead">InitializeListHead</a>
</dt>
<dt>
<a href="kernel.keinitializespinlock">KeInitializeSpinLock</a>
</dt>
<dt>
<a href="kernel.removeheadlist">RemoveHeadList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExInterlockedRemoveHeadList routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

