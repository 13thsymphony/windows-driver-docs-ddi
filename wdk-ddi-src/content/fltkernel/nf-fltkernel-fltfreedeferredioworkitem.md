---
UID: NF:fltkernel.FltFreeDeferredIoWorkItem
title: FltFreeDeferredIoWorkItem function
author: windows-driver-content
description: The FltFreeDeferredIoWorkItem routine frees a work item allocated by the FltAllocateDeferredIoWorkItem routine.
old-location: ifsk\fltfreedeferredioworkitem.htm
old-project: ifsk
ms.assetid: e061c8c3-b0f9-4341-b064-91df43303f70
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_677ca3fc-8c9e-4e3e-8ed4-00a25779913d.xml, FltFreeDeferredIoWorkItem, FltFreeDeferredIoWorkItem routine [Installable File System Drivers], fltkernel/FltFreeDeferredIoWorkItem, ifsk.fltfreedeferredioworkitem
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltFreeDeferredIoWorkItem
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltFreeDeferredIoWorkItem function
The <b>FltFreeDeferredIoWorkItem</b> routine frees a work item allocated by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff541720">FltAllocateDeferredIoWorkItem</a> routine.

## Syntax

```
VOID FLTAPI FltFreeDeferredIoWorkItem(
  PFLT_DEFERRED_IO_WORKITEM FltWorkItem
);
```

## Parameters

`FltWorkItem`

Opaque pointer to the work item to be freed.


## Return Value

None

## Remarks

<b>FltFreeDeferredIoWorkItem</b> frees an opaque FLT_DEFERRED_IO_WORKITEM structure that was allocated by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541720">FltAllocateDeferredIoWorkItem</a>. The freed memory is returned to nonpaged pool. 

The FLT_DEFERRED_IO_WORKITEM structure is opaque: that is, its members are reserved for system use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541720">FltAllocateDeferredIoWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543449">FltQueueDeferredIoWorkItem</a>