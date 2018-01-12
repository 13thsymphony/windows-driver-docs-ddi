---
UID: NF:wdm.IoFreeWorkItem
title: IoFreeWorkItem function
author: windows-driver-content
description: The IoFreeWorkItem routine frees a work item that was allocated by IoAllocateWorkItem.
old-location: kernel\iofreeworkitem.htm
old-project: kernel
ms.assetid: e0b0a4a3-6003-4b48-a3cf-570e5405fa5b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoFreeWorkItem
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
req.alt-api: IoFreeWorkItem
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
req.irql: <= DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoFreeWorkItem function



## -description
The <b>IoFreeWorkItem</b> routine frees a work item that was allocated by <a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a>.



## -syntax

````
VOID IoFreeWorkItem(
  _In_ PIO_WORKITEM IoWorkItem 
);
````


## -parameters

### -param IoWorkItem  [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure that was returned by a previous call to <a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a>.


## -returns
None


## -remarks
Only free a work item that is not currently queued. The system dequeues a work item before it runs the work item's callback routine, so <b>IoFreeWorkItem</b> can be called from within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566380">WorkItem</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff566381">WorkItemEx</a> routine for the work item. 

For more information about work items, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>. 


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
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioallocateworkitem.md">IoAllocateWorkItem</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoFreeWorkItem routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

