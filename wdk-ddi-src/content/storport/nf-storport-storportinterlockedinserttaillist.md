---
UID: NF.storport.StorPortInterlockedInsertTailList
title: StorPortInterlockedInsertTailList function
author: windows-driver-content
description: The StorPortInterlockedInsertTailList routine atomically inserts an entry at the end of a doubly linked list of STOR_LIST_ENTRY structures.
old-location: storage\storportinterlockedinserttaillist.htm
old-project: storage
ms.assetid: 56147D28-B832-4C5D-BFB7-60C4020CA299
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: StorPortInterlockedInsertTailList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: StorPortInterlockedInsertTailList
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

# StorPortInterlockedInsertTailList function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>StorPortInterlockedInsertTailList</b> routine atomically inserts an entry at the end of a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structures.



## -syntax

````
ULONG StorPortInterlockedInsertTailList(
  _In_    PVOID            HwDeviceExtension,
  _Inout_ PSTOR_LIST_ENTRY ListHead,
  _Inout_ PSTOR_LIST_ENTRY ListEntry,
  _Inout_ PSTOR_LIST_ENTRY *Result,
  _Inout_ PSTOR_KSPIN_LOCK Lock
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param ListHead [in, out]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structure that represents the head of the list.


### -param ListEntry [in, out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structure that represents the entry to be inserted into the list. 


### -param *Result [in, out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt790432">STOR_LIST_ENTRY</a> structure that represents the first entry of the list before the new entry was inserted.


### -param Lock [in, out]

A pointer to a <b>STOR_KSPIN_LOCK</b> structure that serves as the spin lock used to synchronize access to the list. The storage for the spin lock must be resident and must have been initialized by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt790427">StorPortInitializeSpinLock</a>.

 You must use this spin lock only with the <b>StorPortInterlocked<i>Xxx</i>List</b> routines.


## -returns
<b>StorPortInterlockedInsertHeadList</b> returns one of the following status codes:
<dl>
<dt><b>STOR_STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This function is not implemented on the active operating system.
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>The list items were removed successfully or the list is already empty.
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>A pointer in <i>ListHead</i> or <i>Result</i> is <b>NULL</b>.

 


## -remarks


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
<a href="kernel.initializelisthead">InitializeListHead</a>
</dt>
<dt>
<a href="kernel.insertheadlist">InsertHeadList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt790427">StorPortInitializeSpinLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt790429">StorPortInterlockedInsertTailList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt790430">StorPortInterlockedRemoveHeadList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortInterlockedInsertTailList routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

