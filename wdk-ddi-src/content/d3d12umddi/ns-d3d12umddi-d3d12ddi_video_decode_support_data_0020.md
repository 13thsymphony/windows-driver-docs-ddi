---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
title: D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
author: windows-driver-content
description: Specifies data used to determine support of hardware for a configuration.
old-location: display\d3d12ddi_video_decode_support_data.htm
old-project: display
ms.assetid: 05274F4B-0473-42BA-A382-B348A85DBFA5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020, D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020, display.d3d12ddi_video_decode_support_data
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020
---

# D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 structure
Specifies data used to determine support of hardware for a configuration.

## Syntax
````
typedef struct D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020 {
  UINT                                           NodeIndex;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020       Configuration;
  UINT                                           Width;
  UINT                                           Height;
  DXGI_FORMAT                                    DecodeFormat;
  DXGI_RATIONAL                                  FrameRate;
  UINT                                           BitRate;
  D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020       SupportFlags;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS_0020 ConfigurationFlags;
  D3D12DDI_VIDEO_DECODE_TIER_0020                DecodeTier;
} D3D12DDI_VIDEO_DECODE_SUPPORT_DATA_0020;
````

## Members


`NodeIndex`

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.

`Configuration`

The decode profile and bitstream encryption.  For more information, see <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a>.

`Width`

The decode width of the source stream.

`Height`

The decode height of the source stream.

`DecodeFormat`

The DirectX resource data format to use as the decode format.  If no decoder conversion is specified, this format is the output format.

`FrameRate`

The frame rate of the video format.  Used to help return performance hints in the <b>SupportFlags</b> member. A value of zero (0) means unknown.

`BitRate`

The average bits per second data compression rate for the compressed video stream.  This is used by the driver to determine whether the video can be decoded in real time. A value of zero (0) means unknown.

`SupportFlags`

Supported flags. For more information, see <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_support_flags_0020.md">D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS</a>.

`ConfigurationFlags`

Configuration flags. For more information, see <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS</a>.

`DecodeTier`

The tier supported by this configuration.  For more information, see <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_tier_0020.md">D3D12DDI_VIDEO_DECODE_TIER</a>.

## Remarks
This structure is retrieved through the <a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_getcaps.md">pfnGetCaps</a> callback function  with the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddicaps_type.md">D3D12DDICAPS_TYPE</a> set to a value of <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_SUPPORT</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020.md">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a>



<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_tier_0020.md">D3D12DDI_VIDEO_DECODE_TIER</a>



<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_decode_support_flags_0020.md">D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS</a>



<b>D3D12DDI_VIDEO_DECODE_CONFIGURATION_FLAGS</b>