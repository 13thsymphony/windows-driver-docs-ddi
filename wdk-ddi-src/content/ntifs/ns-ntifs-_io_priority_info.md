---
UID: NS:ntifs._IO_PRIORITY_INFO
title: "_IO_PRIORITY_INFO"
author: windows-driver-content
description: The IO_PRIORITY_INFO structure is used to hold thread priority information.
old-location: ifsk\io_priority_info.htm
old-project: ifsk
ms.assetid: 1161b239-3ad1-4a0c-9d11-4a3a88d361b3
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: PIO_PRIORITY_INFO structure pointer [Installable File System Drivers], ntifs/PIO_PRIORITY_INFO, PIO_PRIORITY_INFO, ntifs/IO_PRIORITY_INFO, _IO_PRIORITY_INFO, IO_PRIORITY_INFO structure [Installable File System Drivers], othersystemstructures_19a36a9e-6950-4a52-b1e3-e25977777952.xml, ifsk.io_priority_info, *PIO_PRIORITY_INFO, IO_PRIORITY_INFO
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	IO_PRIORITY_INFO
product: Windows
targetos: Windows
req.typenames: "*PIO_PRIORITY_INFO, IO_PRIORITY_INFO"
---

# _IO_PRIORITY_INFO structure
The IO_PRIORITY_INFO structure is used to hold thread priority information.

## Syntax
````
typedef struct _IO_PRIORITY_INFO {
  ULONG            Size;
  ULONG            ThreadPriority;
  ULONG            PagePriority;
  IO_PRIORITY_HINT IoPriority;
} IO_PRIORITY_INFO, *PIO_PRIORITY_INFO;
````

## Members


`IoPriority`

Read-only member used to hold a thread's I/O priority.

`PagePriority`

Read-only member used to hold a thread's paging priority.

`Size`

Read-only member initialized by the <a href="..\ntifs\nf-ntifs-ioinitializepriorityinfo.md">IoInitializePriorityInfo</a> routine.

`ThreadPriority`

Read-only member used to hold a thread's priority.

## Remarks
The IO_PRIORITY_INFO structure is used by the <a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a> and <a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a> routines to save and set a thread's priority state.

A structure of type IO_PRIORITY_INFO must be initialized before first use by calling either the <a href="..\ntifs\nf-ntifs-ioinitializepriorityinfo.md">IoInitializePriorityInfo</a> routine or the <a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This structure is available starting with Windows Vista. This structure is available starting with Windows Vista. |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromthread.md">FltGetIoPriorityHintFromThread</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintocallbackdata.md">FltSetIoPriorityHintIntoCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintofileobject.md">FltSetIoPriorityHintIntoFileObject</a>



<a href="..\fltkernel\nf-fltkernel-fltretrieveiopriorityinfo.md">FltRetrieveIoPriorityInfo</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromfileobject.md">FltGetIoPriorityHintFromFileObject</a>



<a href="..\fltkernel\nf-fltkernel-fltapplypriorityinfothread.md">FltApplyPriorityInfoThread</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhint.md">FltGetIoPriorityHint</a>



<a href="..\ntifs\nf-ntifs-ioinitializepriorityinfo.md">IoInitializePriorityInfo</a>



<a href="..\fltkernel\nf-fltkernel-fltgetiopriorityhintfromcallbackdata.md">FltGetIoPriorityHintFromCallbackData</a>



<a href="..\fltkernel\nf-fltkernel-fltsetiopriorityhintintothread.md">FltSetIoPriorityHintIntoThread</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IO_PRIORITY_INFO structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>