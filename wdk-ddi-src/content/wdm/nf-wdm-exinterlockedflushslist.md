---
UID: NF:wdm.ExInterlockedFlushSList
title: ExInterlockedFlushSList macro
author: windows-driver-content
description: The ExInterlockedFlushSList routine atomically removes all entries from a sequenced singly linked list.
old-location: kernel\exinterlockedflushslist.htm
old-project: kernel
ms.assetid: 98fcada7-5160-4eb2-ac7c-0ab1192340a9
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: ExInterlockedFlushSList, ExInterlockedFlushSList routine [Kernel-Mode Driver Architecture], k102_493935e2-44c7-471b-807f-ca6f110d8155.xml, kernel.exinterlockedflushslist, wdm/ExInterlockedFlushSList
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExInterlockedFlushSList
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExInterlockedFlushSList function
The <b>ExInterlockedFlushSList</b> routine atomically removes all entries from a sequenced singly linked list.

## Syntax

````
PSLIST_ENTRY ExInterlockedFlushSList(
  _Inout_ PSLIST_HEADER ListHead
);
````

## Parameters

`Head`

TBD


## Return Value

None

## Remarks

<b>ExInterlockedFlushSList</b> does not delete the <a href="..\wdm\ns-wdm-_slist_entry.md">SLIST_ENTRY</a> structures that made up the list; it only sets the internal pointer of <i>ListHead</i> to the beginning of the list to <b>NULL</b>. The driver must free the entries explicitly.

The routine returns a pointer to the first <b>SLIST_ENTRY</b> structure that was on the list. The driver can use this pointer to iterate through the entries.

For more information about using this routine to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

Callers of <b>ExInterlockedFlushSList</b> can be running at any IRQL. The storage for the <i>ListHead</i> parameter and the list entries must be resident at all IRQLs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (see Remarks section) |

## See Also

<a href="..\wdm\nf-wdm-initializeslisthead.md">ExInitializeSListHead</a>