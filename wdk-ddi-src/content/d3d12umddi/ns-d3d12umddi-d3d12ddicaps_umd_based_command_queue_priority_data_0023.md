---
UID: NS.D3D12UMDDI.D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023
title: D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023
author: windows-driver-content
description: Contains priority data for a user-mode driver (UMD)-based command queue.
old-location: display\d3d12ddicaps_umd_based_command_queue_priority_data_0023.htm
old-project: display
ms.assetid: B82C6050-689A-4D70-831A-B935EDBBC9AC
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023, D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023
req.alt-loc: D3d12umddi.h
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
---

# D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023 structure



## -description
Contains  priority data for a user-mode driver (UMD)-based command queue.


## -syntax

````
typedef struct D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023 {
  D3D12DDI_COMMAND_QUEUE_FLAGS SupportedQueueFlagsForGlobalRealtimeQueues;
} D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023;
````


## -struct-fields

### -field SupportedQueueFlagsForGlobalRealtimeQueues

Supported queue flags for global real-time queues.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>