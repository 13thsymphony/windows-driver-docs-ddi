---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_DECODE_TIER_0020
title: D3D12DDI_VIDEO_DECODE_TIER_0020
author: windows-driver-content
description: Specifies the video decode tier.
old-location: display\d3d12ddi_video_decode_tier.htm
old-project: display
ms.assetid: CC4B83A3-1F57-493F-840F-F0F799B631E6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_1, D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020, D3D12DDI_VIDEO_DECODE_TIER_0020_3, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_2, d3d12umddi/D3D12DDI_VIDEO_DECODE_TIER_0020_3, D3D12DDI_VIDEO_DECODE_TIER_0020_2, D3D12DDI_VIDEO_DECODE_TIER_0020_1, display.d3d12ddi_video_decode_tier, D3D12DDI_VIDEO_DECODE_TIER_0020 enumeration [Display Devices], D3D12DDI_VIDEO_DECODE_TIER_0020
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
-	D3D12DDI_VIDEO_DECODE_TIER_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_TIER_0020
---

# D3D12DDI_VIDEO_DECODE_TIER_0020 Enumeration
Specifies the video decode tier.

## Syntax
````
typedef enum D3D12DDI_VIDEO_DECODE_TIER_0020 { 
  D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED  = 0,
  D3D12DDI_VIDEO_DECODE_TIER_0020_1              = 1,
  D3D12DDI_VIDEO_DECODE_TIER_0020_2              = 2,
  D3D12DDI_VIDEO_DECODE_TIER_0020_3              = 3
} D3D12DDI_VIDEO_DECODE_TIER_0020;
````

## Constants

<table>
            
                <tr>
                    <td>D3D12DDI_VIDEO_DECODE_TIER_0020_1</td>
                    <td>Video decode tier 1.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_DECODE_TIER_0020_2</td>
                    <td>Video decode tier 2.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_DECODE_TIER_0020_3</td>
                    <td>Video decode tier 3.</td>
                </tr>
            
                <tr>
                    <td>D3D12DDI_VIDEO_DECODE_TIER_0020_NOT_SUPPORTED</td>
                    <td>The decode profile is not supported.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |