---
UID: NF:wdm.RemoveTailList
title: RemoveTailList function
author: windows-driver-content
description: The RemoveTailList routine removes an entry from the end of a doubly linked list of LIST_ENTRY structures.
old-location: kernel\removetaillist.htm
old-project: kernel
ms.assetid: 67942bf7-28f6-4b2d-a880-9439afaf0bb2
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RemoveTailList, RemoveTailList routine [Kernel-Mode Driver Architecture], k109_b9ce310f-ead1-46ee-a591-ae018f61f536.xml, kernel.removetaillist, wdm/RemoveTailList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	RemoveTailList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RemoveTailList function
The <b>RemoveTailList</b> routine removes an entry from the end of a doubly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structures.

## Syntax

````
PLIST_ENTRY RemoveTailList(
  _Inout_ PLIST_ENTRY ListHead
);
````

## Parameters

`ListHead`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554296">LIST_ENTRY</a> structure that serves as the list header.


## Return Value

<b>RemoveTailList</b> returns a pointer to the entry that was at the tail of the list. If the list is empty, <b>RemoveTailList</b> returns <i>ListHead</i>.

## Remarks

<b>RemoveTailList</b> removes the last entry from the list by setting <i>ListHead</i>-&gt;<b>Blink</b> to point to the second-to-last entry in the list. The routine sets the <b>Flink</b> member of the new first entry to <i>ListHead</i>. In the event the list is empty, this is effectively a no-op.

For information about using this routine when implementing a doubly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>InsertHeadList</b> can be running at any IRQL. If <b>InsertHeadList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h) |
| **IRQL** | Any level (See Remarks section) |

## See Also

<a href="..\wudfwdm\nf-wudfwdm-islistempty.md">IsListEmpty</a>



<a href="..\wudfwdm\nf-wudfwdm-removeentrylist.md">RemoveEntryList</a>



<a href="..\wudfwdm\nf-wudfwdm-removeheadlist.md">RemoveHeadList</a>



<a href="..\wudfwdm\nf-wudfwdm-initializelisthead.md">InitializeListHead</a>