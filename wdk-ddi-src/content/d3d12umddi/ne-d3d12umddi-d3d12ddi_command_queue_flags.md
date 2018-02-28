---
UID: NE:d3d12umddi.D3D12DDI_COMMAND_QUEUE_FLAGS
title: D3D12DDI_COMMAND_QUEUE_FLAGS
author: windows-driver-content
description: Contains values for the video command queue.
old-location: display\d3d12ddi_command_queue_flags.htm
old-project: display
ms.assetid: A5EFE133-6F63-4EA4-8F7F-B2B6A4E1838C
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_COMMAND_QUEUE_FLAGS, D3D12DDI_COMMAND_QUEUE_FLAGS enumeration [Display Devices], D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE, D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS, D3D12DDI_COMMAND_QUEUE_FLAG_3D, D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE, D3D12DDI_COMMAND_QUEUE_FLAG_COPY, D3D12DDI_COMMAND_QUEUE_FLAG_NONE, D3D12DDI_COMMAND_QUEUE_FLAG_PAGING, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAGS, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_3D, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_COPY, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_NONE, d3d12umddi/D3D12DDI_COMMAND_QUEUE_FLAG_PAGING, display.d3d12ddi_command_queue_flags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_COMMAND_QUEUE_FLAGS
product: Windows
targetos: Windows
req.typenames: D3D12DDI_COMMAND_QUEUE_FLAGS
---

# D3D12DDI_COMMAND_QUEUE_FLAGS Enumeration
Contains values for the video command queue.

## Syntax
````
typedef enum D3D12DDI_COMMAND_QUEUE_FLAGS { 
  D3D12DDI_COMMAND_QUEUE_FLAG_NONE                = 0x00000000,
  D3D12DDI_COMMAND_QUEUE_FLAG_3D                  = 0x00000001,
  D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE             = 0x00000002,
  D3D12DDI_COMMAND_QUEUE_FLAG_COPY                = 0x00000004,
  D3D12DDI_COMMAND_QUEUE_FLAG_PAGING              = 0x00000008,
  D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE   = 0x00000010,
  D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS  = 0x00000020
} D3D12DDI_COMMAND_QUEUE_FLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_COMMAND_QUEUE_FLAG_0020_VIDEO_LEGACY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_DECODE</td>
                    <td>Decode video.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_COMMAND_QUEUE_FLAG_0022_VIDEO_PROCESS</td>
                    <td>Process video.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_COMMAND_QUEUE_FLAG_3D</td>
                    <td>3D.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_COMMAND_QUEUE_FLAG_COMPUTE</td>
                    <td>Compute.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_COMMAND_QUEUE_FLAG_COPY</td>
                    <td>Copy.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_COMMAND_QUEUE_FLAG_NONE</td>
                    <td>No flags.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_COMMAND_QUEUE_FLAG_PAGING</td>
                    <td>Paging.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |