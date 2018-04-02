---
UID: NF:wudfwdm.PushEntryList
title: PushEntryList function
author: windows-driver-content
description: The PushEntryList routine inserts an entry at the beginning of a singly linked list of SINGLE_LIST_ENTRY structures.
old-location: kernel\pushentrylist.htm
old-project: kernel
ms.assetid: 19f387d3-6c00-4c71-8114-61c53654613c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PushEntryList, PushEntryList routine [Kernel-Mode Driver Architecture], k109_17626baa-0fb7-4492-9e9c-a25b78b808fb.xml, kernel.pushentrylist, wdm/PushEntryList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfwdm.h
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
req.lib: NtosKrnl.exe
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
-	PushEntryList
product:
- Windows
targetos: Windows
req.typenames: PO_FX_PERF_STATE_UNIT, *PPO_FX_PERF_STATE_UNIT
req.product: Windows 10 or later.
---


# PushEntryList function
The <b>PushEntryList</b> routine inserts an entry at the beginning of a singly linked list of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structures.

## Syntax

````
VOID PushEntryList(
  _Inout_ PSINGLE_LIST_ENTRY ListHead,
  _Inout_ PSINGLE_LIST_ENTRY Entry
);
````

## Parameters

`ListHead`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563799">SINGLE_LIST_ENTRY</a> structure that serves as the list header.

`Entry`

Pointer to SINGLE_LIST_ENTRY structure that represents the entry to be inserted on the list.


## Return Value

None

## Remarks

<b>PushEntryList</b> sets <i>ListHead</i>-&gt;<b>Next</b> to <i>Entry</i>, and <i>Entry</i>-&gt;<b>Next</b> to point to the old first entry of the list.

For information about using this routine when implementing a singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>PushEntryList</b> can be running at any IRQL. If <b>PushEntryList</b> is called at IRQL &gt;= DISPATCH_LEVEL, the storage for <i>ListHead</i> and the list entries must be resident.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wudfwdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any level (See Remarks section) |

## See Also

<a href="..\wudfwdm\nf-wudfwdm-popentrylist.md">PopEntryList</a>



<a href="..\wdm\nf-wdm-exinterlockedpushentrylist.md">ExInterlockedPushEntryList</a>