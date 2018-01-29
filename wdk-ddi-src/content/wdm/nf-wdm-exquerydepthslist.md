---
UID : NF:wdm.ExQueryDepthSList
title : ExQueryDepthSList function
author : windows-driver-content
description : The ExQueryDepthSList routine returns the number of entries currently in a given sequenced singly linked list.
old-location : kernel\exquerydepthslist.htm
old-project : kernel
ms.assetid : fdf40535-4e0d-4db9-9e95-744029eb2bd5
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ExQueryDepthSList, kernel.exquerydepthslist, wdm/ExQueryDepthSList, ExQueryDepthSList routine [Kernel-Mode Driver Architecture], k102_14e2b5cb-bc6a-43f7-a0b2-1fcd8fd414a7.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : <= DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# ExQueryDepthSList function
The <b>ExQueryDepthSList</b> routine returns the number of entries currently in a given sequenced singly linked list.

## Syntax

````
USHORT ExQueryDepthSList(
  _In_ PSLIST_HEADER SListHead
);
````

## Parameters

`SListHead`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563810">SLIST_HEADER</a> structure that serves as the header for the sequenced singly linked list. <i>SListHead</i> must have been initialized by calling <a href="..\wdm\nf-wdm-initializeslisthead.md">ExInitializeSListHead</a>.


## Return Value

<b>ExQueryDepthSList</b> returns the current number of entries in the list.

## Remarks

For more information about using this routine to implement a sequenced singly linked list, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563802">Singly and Doubly Linked Lists</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-exinterlockedpopentryslist.md">ExInterlockedPopEntrySList</a>

<a href="..\wdm\nf-wdm-exinterlockedpushentryslist.md">ExInterlockedPushEntrySList</a>

<a href="..\wdm\nf-wdm-initializeslisthead.md">ExInitializeSListHead</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExQueryDepthSList routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>