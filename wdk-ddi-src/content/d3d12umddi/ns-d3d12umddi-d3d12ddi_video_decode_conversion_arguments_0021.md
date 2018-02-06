---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021
title: D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021
author: windows-driver-content
description: Specifies the arguments for decode output conversion.
old-location: display\d3d12ddi_video_decode_conversion_arguments.htm
old-project: display
ms.assetid: 01288B0F-4095-4642-9DA9-4E14B0BCBB18
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021, display.d3d12ddi_video_decode_conversion_arguments, d3d12umddi/D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021, D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021 structure [Display Devices]
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
-	D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021
---

# D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021 structure
Specifies the arguments for decode output conversion.

## Syntax
````
typedef struct D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021 {
  BOOL                  Enable;
  D3D12DDI_HRESOURCE    hDrvReferenceTexture2D;
  UINT                  ReferenceSubresource;
  DXGI_COLOR_SPACE_TYPE OutputColorSpace;
  DXGI_COLOR_SPACE_TYPE DecodeColorSpace;
} D3D12DDI_VIDEO_DECODE_CONVERSION_ARGUMENTS_0021;
````

## Members


`DecodeColorSpace`

The source decoded color space before conversion.

`Enable`

Indicates whether decode conversion should be used.

`hDrvReferenceTexture2D`

If down sampling is enabled, the output at decode resolution, color space, and format may be required for future decode submissions.  If it is not needed, specify null.

`OutputColorSpace`

The target color space of the output.

`ReferenceSubresource`

The subresource index to use of the <i>hDrvReferenceTexture2D</i> argument.

## Remarks
Scaling is specified by the difference in reference texture size versus the output texture size.

Use <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_CONVERSION_SUPPORT</b> to determine if a conversion combination is supported. 

A source and destination resolution and format are communicated by the resource properties of reference textures versus the output buffer specified in the pfnDecodeFrame callback function.

Support for scaling and format conversion during decode can also be queried with <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_CONVERSION_SUPPORT</b>.  The source size for the scale is the source stream width and height set during video decoder creation.  The output size for the scale is the width and height of the output texture passed into the pfnDecodeFrame callback function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |