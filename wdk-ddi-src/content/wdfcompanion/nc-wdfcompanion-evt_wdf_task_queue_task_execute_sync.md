---
UID: NC.wdfcompanion.EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC
title: EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC
author: windows-driver-content
description: For internal use only.
old-location: wdf\evt_wdf_task_queue_task_execute_sync.htm
old-project: wdf
ms.assetid: c45d1873-fb29-49ee-b99b-09861478ac89
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_COMMON_BUFFER_CONFIG, WDF_COMMON_BUFFER_CONFIG, *PWDF_COMMON_BUFFER_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
req.alt-api: EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC
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

# EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC callback



## -description

			For internal use only.


## -prototype

````
EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC;

NTSTATUS EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC(
  _In_      WDFTASKQUEUE Queue,
  _In_opt_  PVOID        InputBuffer,
  _Out_opt_ PVOID        OutputBuffer,
  _In_      size_t       InputBufferLength,
  _In_      size_t       OutputBufferLength,
  _In_      size_t       *BytesWritten,
  _In_      ULONG        TaskOperationCode
)
{ ... }
````


## -parameters

### -param Queue [in]


### -param InputBuffer [in, optional]


### -param OutputBuffer [out, optional]


### -param InputBufferLength [in]


### -param OutputBufferLength [in]


### -param BytesWritten [in]


### -param TaskOperationCode [in]


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