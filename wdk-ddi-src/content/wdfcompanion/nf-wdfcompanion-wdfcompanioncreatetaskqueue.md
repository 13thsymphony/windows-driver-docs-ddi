---
UID: NF:wdfcompanion.WdfCompanionCreateTaskQueue
title: WdfCompanionCreateTaskQueue function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfcompanioncreatetaskqueue.htm
old-project: wdf
ms.assetid: 05298ffe-75e5-444e-9843-54dd063f59f5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfCompanionCreateTaskQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
req.alt-api: WdfCompanionCreateTaskQueue
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
req.typenames: WDF_TASK_QUEUE_DISPATCH_TYPE
req.product: Windows 10 or later.
---

# WdfCompanionCreateTaskQueue function



## -description

			For internal use only.



## -syntax

````
NTSTATUS WdfCompanionCreateTaskQueue(
  _In_      WDFCOMPANION           Companion,
  _In_      PWDF_TASK_QUEUE_CONFIG Config,
  _In_opt_  PWDF_OBJECT_ATTRIBUTES QueueAttributes,
  _Out_opt_ WDFTASKQUEUE           *Queue
);
````


## -parameters

### -param Companion [in]


### -param Config [in]


### -param QueueAttributes [in, optional]


### -param Queue [out, optional]


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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>