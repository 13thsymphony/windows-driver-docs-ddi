---
UID: NF:storport.StorPortQueueWorkItem
title: StorPortQueueWorkItem function
author: windows-driver-content
description: Schedules a Storport work item to execute within the context of a system worker thread.
old-location: storage\storportqueueworkitem.htm
old-project: storage
ms.assetid: 7B5DD97C-2E3D-4FF7-BF04-36F016B0C6B3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: StorPortQueueWorkItem, StorPortQueueWorkItem routine [Storage Devices], storage.storportqueueworkitem, storport/StorPortQueueWorkItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	storport.h
api_name:
-	StorPortQueueWorkItem
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortQueueWorkItem function
Schedules a Storport work item to execute within the context of  a system worker thread.

## Syntax

```
ULONG StorPortQueueWorkItem(
  PVOID        HwDeviceExtension,
  PHW_WORKITEM WorkItemCallback,
  PVOID        Worker,
  PVOID        Context
);
```

## Parameters

`HwDeviceExtension`

A pointer to the hardware device extension for the host bus adapter (HBA).

`WorkItemCallback`

A pointer to a work item callback routine supplied by the miniport. This routine is called in context of the system thread to process the scheduled <i>WorkItem</i>.

`Worker`

A pointer to an opaque buffer for the worker returned by <a href="https://msdn.microsoft.com/library/windows/hardware/hh451486">StorPortInitializeWorker</a>.

`Context`

Optional context for the <i>WorkItem</i> that is processed by the callback routine in <i>WorkItemCallback</i>.


## Return Value

The <b>StorPortQueueWorkItem</b> routine returns one of these status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_IRQL</b></dt>
</dl>
</td>
<td width="60%">
Current IRQL &gt; DISPATCH_LEVEL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>HwDeviceExtension</i>, <i>Worker</i>, or <i>WorkItemCallback</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_BUSY</b></dt>
</dl>
</td>
<td width="60%">
The work item was is already queued for processing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The work item was successfully queued.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 8 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451320">HwStorWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451478">StorPortFreeWorker</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451486">StorPortInitializeWorker</a>