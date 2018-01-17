---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020
title: D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020
author: windows-driver-content
description: Contains the video decode parameter type.
old-location: display\d3d12ddi_video_decode_parameter_type.htm
old-project: display
ms.assetid: 4ED18E79-2BEA-4FB5-BDA4-B5CA59D6E1A8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020, D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020
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
req.alt-api: D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020
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
req.typenames: D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020
---

# D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020 enumeration



## -description
Contains the video decode parameter type. 



## -syntax

````
typedef enum D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020 { 
  D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_PICTURE_PARAMETERS           = 0,
  D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_INVERSE_QUANTIZATION_MATRIX  = 1,
  D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_SLICE_CONTROL                = 2
} D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020;
````


## -enum-fields

### -field D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_PICTURE_PARAMETERS

Picture decoding parameter buffer.


### -field D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_INVERSE_QUANTIZATION_MATRIX

Inverse quantization matrix buffer.


### -field D3D12DDI_VIDEO_DECODE_PARAMETER_TYPE_0020_SLICE_CONTROL

Slice control buffer.


## -remarks
The definition of each buffer type is dependent upon the decode profile and is defined in each codec specification.</p>