---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022
title: D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022
author: windows-driver-content
description: Contains values that specify whether the conversion from the source format and color space to destination format and color space is supported.
old-location: display\d3d12ddi_video_process_support_flags.htm
old-project: display
ms.assetid: 2E6E1F22-C6E8-4290-A342-B01387633D43
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d12umddi/D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022, display.d3d12ddi_video_process_support_flags, d3d12umddi/D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAG_0022_NONE, D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022 enumeration [Display Devices], D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAG_0022_SUPPORTED, D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022, d3d12umddi/D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAG_0022_SUPPORTED, D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAG_0022_NONE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022
---

# D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022 Enumeration
Contains values that specify whether the conversion from the source format and color space to destination format and color space is supported.

## Syntax
````
typedef enum D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022 { 
  D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAG_0022_NONE       = 0,
  D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAG_0022_SUPPORTED  = 0x1
} D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022;
````

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAG_0022_NONE</td>
                    <td>The conversion from the source format and color space to destination format and color space is not supported.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAG_0022_SUPPORTED</td>
                    <td>The conversion from the source format and color space to destination format and color space is supported.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |