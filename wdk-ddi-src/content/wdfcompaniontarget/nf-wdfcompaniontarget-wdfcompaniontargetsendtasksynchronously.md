---
UID: NF.wdfcompaniontarget.WdfCompanionTargetSendTaskSynchronously
title: WdfCompanionTargetSendTaskSynchronously function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfcompaniontargetsendtasksynchronously.htm
old-project: wdf
ms.assetid: d58a275a-aaaa-4159-ba00-6998b7a63434
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfCompanionTargetSendTaskSynchronously
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
req.alt-api: WdfCompanionTargetSendTaskSynchronously
req.alt-loc: wdfcompaniontarget.h
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

# WdfCompanionTargetSendTaskSynchronously function



## -description

			For internal use only.


## -syntax

````
NTSTATUS WdfCompanionTargetSendTaskSynchronously(
  _In_     WDFCOMPANIONTARGET     CompanionTarget,
  _In_     USHORT                 TaskQueueIdentifier,
  _In_     ULONG                  TaskOperationCode,
  _In_opt_ PWDF_MEMORY_DESCRIPTOR InputBuffer,
  _In_opt_ PWDF_MEMORY_DESCRIPTOR OutputBuffer,
  _In_opt_ PWDF_TASK_SEND_OPTIONS TaskOptions,
  _Out_    PULONG_PTR             BytesReturned
);
````


## -parameters

### -param CompanionTarget [in]


### -param TaskQueueIdentifier [in]


### -param TaskOperationCode [in]


### -param InputBuffer [in, optional]


### -param OutputBuffer [in, optional]


### -param TaskOptions [in, optional]


### -param BytesReturned [out]


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.23
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfcompaniontarget.h</dt>
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