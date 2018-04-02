---
UID: NF:wdfcompaniontarget.WdfCompanionTargetSendTaskSynchronously
title: WdfCompanionTargetSendTaskSynchronously function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfcompaniontargetsendtasksynchronously.htm
old-project: wdf
ms.assetid: d58a275a-aaaa-4159-ba00-6998b7a63434
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfCompanionTargetSendTaskSynchronously, WdfCompanionTargetSendTaskSynchronously method, wdf.wdfcompaniontargetsendtasksynchronously, wdfcompaniontarget/WdfCompanionTargetSendTaskSynchronously
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcompaniontarget.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.23
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfcompaniontarget.h
api_name:
-	WdfCompanionTargetSendTaskSynchronously
product:
- Windows
targetos: Windows
req.typenames: WDF_TASK_SEND_OPTIONS_FLAGS
req.product: Windows 10 or later.
---


# WdfCompanionTargetSendTaskSynchronously function
For internal use only.

## Syntax

```
NTSTATUS WdfCompanionTargetSendTaskSynchronously(
  WDFCOMPANIONTARGET     CompanionTarget,
  USHORT                 TaskQueueIdentifier,
  ULONG                  TaskOperationCode,
  PWDF_MEMORY_DESCRIPTOR InputBuffer,
  PWDF_MEMORY_DESCRIPTOR OutputBuffer,
  PWDF_TASK_SEND_OPTIONS TaskOptions,
  PULONG_PTR             BytesReturned
);
```

## Parameters

`CompanionTarget`



`TaskQueueIdentifier`



`TaskOperationCode`



`InputBuffer`



`OutputBuffer`



`TaskOptions`



`BytesReturned`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.23 |
| **Header** | wdfcompaniontarget.h |
| **IRQL** | PASSIVE_LEVEL |