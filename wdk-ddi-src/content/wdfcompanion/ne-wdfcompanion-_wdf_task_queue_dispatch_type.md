---
UID: NE:wdfcompanion._WDF_TASK_QUEUE_DISPATCH_TYPE
title: "_WDF_TASK_QUEUE_DISPATCH_TYPE"
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_task_queue_dispatch_type.htm
old-project: wdf
ms.assetid: 27cc4067-33de-4f2d-abad-05c73c875458
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfTaskQueueDispatchMax, WdfTaskQueueDispatchSequential, wdfcompanion/WdfTaskQueueDispatchMax, WdfTaskQueueDispatchParallel, wdfcompanion/WdfTaskQueueDispatchInvalid, wdfcompanion/WdfTaskQueueDispatchSequential, wdfcompanion/WdfTaskQueueDispatchParallel, WDF_TASK_QUEUE_DISPATCH_TYPE enumeration, WdfTaskQueueDispatchInvalid, WDF_TASK_QUEUE_DISPATCH_TYPE, wdfcompanion/WDF_TASK_QUEUE_DISPATCH_TYPE, _WDF_TASK_QUEUE_DISPATCH_TYPE, wdf.wdf_task_queue_dispatch_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfcompanion.h
apiname:
-	WDF_TASK_QUEUE_DISPATCH_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_TASK_QUEUE_DISPATCH_TYPE
req.product: Windows 10 or later.
---

# _WDF_TASK_QUEUE_DISPATCH_TYPE Enumeration
For internal use only.

## Syntax
````
typedef enum _WDF_TASK_QUEUE_DISPATCH_TYPE { 
  WdfTaskQueueDispatchInvalid     = 0,
  WdfTaskQueueDispatchSequential,
  WdfTaskQueueDispatchParallel,
  WdfTaskQueueDispatchMax
} WDF_TASK_QUEUE_DISPATCH_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>WdfTaskQueueDispatchInvalid</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WdfTaskQueueDispatchMax</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WdfTaskQueueDispatchParallel</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WdfTaskQueueDispatchSequential</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum UMDF version** | 2.23 |
| **Header** | wdfcompanion.h |