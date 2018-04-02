---
UID: NS:ntifs._IO_PRIORITY_INFO
title: "_IO_PRIORITY_INFO"
author: windows-driver-content
description: The IO_PRIORITY_INFO structure is used to hold thread priority information.
old-location: ifsk\io_priority_info.htm
old-project: ifsk
ms.assetid: 1161b239-3ad1-4a0c-9d11-4a3a88d361b3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PIO_PRIORITY_INFO, IO_PRIORITY_INFO, IO_PRIORITY_INFO structure [Installable File System Drivers], PIO_PRIORITY_INFO, PIO_PRIORITY_INFO structure pointer [Installable File System Drivers], _IO_PRIORITY_INFO, ifsk.io_priority_info, ntifs/IO_PRIORITY_INFO, ntifs/PIO_PRIORITY_INFO, othersystemstructures_19a36a9e-6950-4a52-b1e3-e25977777952.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available starting with Windows Vista.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	IO_PRIORITY_INFO
product: Windows
targetos: Windows
req.typenames: IO_PRIORITY_INFO, *PIO_PRIORITY_INFO
---

# _IO_PRIORITY_INFO structure
The IO_PRIORITY_INFO structure is used to hold thread priority information.

## Syntax
```
typedef struct _IO_PRIORITY_INFO {
  ULONG            Size;
  ULONG            ThreadPriority;
  ULONG            PagePriority;
  IO_PRIORITY_HINT IoPriority;
} *PIO_PRIORITY_INFO, IO_PRIORITY_INFO;
```

## Members


`Size`

Read-only member initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548424">IoInitializePriorityInfo</a> routine.

`ThreadPriority`

Read-only member used to hold a thread's priority.

`PagePriority`

Read-only member used to hold a thread's paging priority.

`IoPriority`

Read-only member used to hold a thread's I/O priority.

## Remarks
The IO_PRIORITY_INFO structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff541766">FltApplyPriorityInfoThread</a> routines to save and set a thread's priority state.

A structure of type IO_PRIORITY_INFO must be initialized before first use by calling either the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548424">IoInitializePriorityInfo</a> routine or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541766">FltApplyPriorityInfoThread</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This structure is available starting with Windows Vista. This structure is available starting with Windows Vista. |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541766">FltApplyPriorityInfoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543065">FltGetIoPriorityHint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543068">FltGetIoPriorityHintFromCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543074">FltGetIoPriorityHintFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543080">FltGetIoPriorityHintFromThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544354">FltRetrieveIoPriorityInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544526">FltSetIoPriorityHintIntoCallbackData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544530">FltSetIoPriorityHintIntoFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544534">FltSetIoPriorityHintIntoThread</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548424">IoInitializePriorityInfo</a>