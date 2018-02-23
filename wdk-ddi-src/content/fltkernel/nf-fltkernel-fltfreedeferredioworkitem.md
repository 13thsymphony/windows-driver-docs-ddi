---
UID: NF:fltkernel.FltFreeDeferredIoWorkItem
title: FltFreeDeferredIoWorkItem function
author: windows-driver-content
description: The FltFreeDeferredIoWorkItem routine frees a work item allocated by the FltAllocateDeferredIoWorkItem routine.
old-location: ifsk\fltfreedeferredioworkitem.htm
old-project: ifsk
ms.assetid: e061c8c3-b0f9-4341-b064-91df43303f70
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_e_to_o_677ca3fc-8c9e-4e3e-8ed4-00a25779913d.xml, fltkernel/FltFreeDeferredIoWorkItem, FltFreeDeferredIoWorkItem, FltFreeDeferredIoWorkItem routine [Installable File System Drivers], ifsk.fltfreedeferredioworkitem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: FltMgr.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	FltMgr.lib
-	FltMgr.dll
apiname:
-	FltFreeDeferredIoWorkItem
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltFreeDeferredIoWorkItem function
The <b>FltFreeDeferredIoWorkItem</b> routine frees a work item allocated by the <a href="..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md">FltAllocateDeferredIoWorkItem</a> routine.

## Syntax

````
VOID FltFreeDeferredIoWorkItem(
  _In_ PFLT_DEFERRED_IO_WORKITEM FltWorkItem
);
````

## Parameters

`FltWorkItem`

Opaque pointer to the work item to be freed.


## Return Value

None

## Remarks

<b>FltFreeDeferredIoWorkItem</b> frees an opaque FLT_DEFERRED_IO_WORKITEM structure that was allocated by a previous call to <a href="..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md">FltAllocateDeferredIoWorkItem</a>. The freed memory is returned to nonpaged pool. 

The FLT_DEFERRED_IO_WORKITEM structure is opaque: that is, its members are reserved for system use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md">FltAllocateDeferredIoWorkItem</a>



<a href="..\fltkernel\nf-fltkernel-fltqueuedeferredioworkitem.md">FltQueueDeferredIoWorkItem</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFreeDeferredIoWorkItem routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>