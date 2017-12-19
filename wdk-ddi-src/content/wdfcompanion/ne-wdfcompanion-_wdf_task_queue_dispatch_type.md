---
UID: NE.wdfcompanion._WDF_TASK_QUEUE_DISPATCH_TYPE
title: _WDF_TASK_QUEUE_DISPATCH_TYPE
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_task_queue_dispatch_type.htm
old-project: wdf
ms.assetid: 27cc4067-33de-4f2d-abad-05c73c875458
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDF_TASK_QUEUE_DISPATCH_TYPE, WDF_TASK_QUEUE_DISPATCH_TYPE
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
req.alt-api: WDF_TASK_QUEUE_DISPATCH_TYPE
req.alt-loc: wdfcompanion.h
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
req.product: Windows 10 or later.
---

# _WDF_TASK_QUEUE_DISPATCH_TYPE enumeration



## -description
For internal use only.



## -syntax

````
typedef enum _WDF_TASK_QUEUE_DISPATCH_TYPE { 
  WdfTaskQueueDispatchInvalid     = 0,
  WdfTaskQueueDispatchSequential,
  WdfTaskQueueDispatchParallel,
  WdfTaskQueueDispatchMax
} WDF_TASK_QUEUE_DISPATCH_TYPE;
````


## -enum-fields

### -field WdfTaskQueueDispatchInvalid


### -field WdfTaskQueueDispatchSequential


### -field WdfTaskQueueDispatchParallel


### -field WdfTaskQueueDispatchMax


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.23

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfcompanion.h</dt>
</dl>
</td>
</tr>
</table>