---
UID: NS:wdfcompanion._WDF_TASK_QUEUE_CONFIG
title: "_WDF_TASK_QUEUE_CONFIG"
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_task_queue_config.htm
old-project: wdf
ms.assetid: a58dd106-dec8-4444-9783-eb16e969ea42
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_TASK_QUEUE_CONFIG, PWDF_TASK_QUEUE_CONFIG, PWDF_TASK_QUEUE_CONFIG structure pointer, WDF_TASK_QUEUE_CONFIG, WDF_TASK_QUEUE_CONFIG structure, _WDF_TASK_QUEUE_CONFIG, wdf.wdf_task_queue_config, wdfcompanion/PWDF_TASK_QUEUE_CONFIG, wdfcompanion/WDF_TASK_QUEUE_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfcompanion.h
api_name:
-	WDF_TASK_QUEUE_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_TASK_QUEUE_CONFIG, *PWDF_TASK_QUEUE_CONFIG
req.product: Windows 10 or later.
---

# _WDF_TASK_QUEUE_CONFIG structure
For internal use only.

## Syntax
```
typedef struct _WDF_TASK_QUEUE_CONFIG {
  ULONG                                Size;
  USHORT                               TaskQueueId;
  WDF_TASK_QUEUE_DISPATCH_TYPE         DispatchType;
  PFN_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC EvtTaskExecuteSync;
} WDF_TASK_QUEUE_CONFIG, *PWDF_TASK_QUEUE_CONFIG;
```

## Members


`Size`



`TaskQueueId`



`DispatchType`



`EvtTaskExecuteSync`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum UMDF version** | 2.23 |
| **Header** | wdfcompanion.h |