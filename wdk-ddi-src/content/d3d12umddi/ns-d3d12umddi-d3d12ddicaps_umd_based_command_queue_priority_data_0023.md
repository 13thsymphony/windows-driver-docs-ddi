---
UID: NS:d3d12umddi.D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023
title: D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023
author: windows-driver-content
description: Contains priority data for a user-mode driver (UMD)-based command queue.
old-location: display\d3d12ddicaps_umd_based_command_queue_priority_data_0023.htm
old-project: display
ms.assetid: B82C6050-689A-4D70-831A-B935EDBBC9AC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023, d3d12umddi/D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023, display.d3d12ddicaps_umd_based_command_queue_priority_data_0023, D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023 structure [Display Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023
product: Windows
targetos: Windows
req.typenames: D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023
---

# D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023 structure
Contains  priority data for a user-mode driver (UMD)-based command queue.

## Syntax
````
typedef struct D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023 {
  D3D12DDI_COMMAND_QUEUE_FLAGS SupportedQueueFlagsForGlobalRealtimeQueues;
} D3D12DDICAPS_UMD_BASED_COMMAND_QUEUE_PRIORITY_DATA_0023;
````

## Members


`SupportedQueueFlagsForGlobalRealtimeQueues`

Supported queue flags for global real-time queues.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |