---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
title: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
author: windows-driver-content
description: Specifies information used to check whether a color space conversion, format conversion, and scale are supported and whether it is required for real-time reasons or reference buffer format.
old-location: display\d3d12ddi_video_decode_conversion_support_data.htm
old-project: display
ms.assetid: E9FA4CEB-84D3-42A6-B36A-B411922F19AE
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022, D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022, display.d3d12ddi_video_decode_conversion_support_data
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
-	D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
---

# D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 structure
Specifies information used to check whether a color space conversion, format conversion, and scale are supported and whether it is required for real-time reasons or reference buffer format.

## Syntax
```
typedef struct D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 {
  UINT                                                NodeIndex;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020            Configuration;
  D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020              DecodeSample;
  D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020              OutputFormat;
  DXGI_RATIONAL                                       FrameRate;
  UINT                                                BitRate;
  D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS_0020 SupportFlags;
  D3D12DDI_VIDEO_SCALE_SUPPORT_0022                   ScaleSupport;
};
```

## Members


`NodeIndex`

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.

`Configuration`

The decode profile and bitstream encryption.  For more information, see the  <a href="https://msdn.microsoft.com/33BD5E1F-75F3-44DC-AE83-A22992CAB6B5">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a> enumeration.

`DecodeSample`

The source decoded as sample description.  For more information, see the  <a href="https://msdn.microsoft.com/B9918A06-6C10-4AD7-97EC-4FA0BC5319AD">D3D12DDI_VIDEO_SAMPLE_DESCRIPTION</a> structure.

`OutputFormat`

The output sample description.  For more information, see the  <a href="https://msdn.microsoft.com/47C0C369-B31B-4291-A420-A1E75BA990CF">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a> structure.

`FrameRate`

The frame rate of the video content. This is used by the driver to determine whether the video can be decoded in real time.

`BitRate`

The average bits per second data compression rate for the compressed video stream.  This is used by the driver to determine whether the video can be decoded in real time.

`SupportFlags`

The returned supported flags. For more information, see the <a href="https://msdn.microsoft.com/7E272786-ECD4-4DF0-A36A-B27454E3E896">D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS</a> enumeration.

`ScaleSupport`

The returned supported output size range for decode conversion.  For more information, see the <a href="https://msdn.microsoft.com/70FFDE9E-2029-4C84-9DEE-C2E81FEE5590">D3D12DDI_VIDEO_SCALE_SUPPORT</a> structure.

## Remarks
The check is made through <a href="https://msdn.microsoft.com/6875B754-115F-481D-8D46-2A383BA6B5E7">pfnGetCaps</a> with the <a href="https://msdn.microsoft.com/C74697BF-A191-4371-9F23-7F655EBC53B3">D3D12DDICAPS_TYPE</a> set to a value of <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_CONVERSION_SUPPORT</b>.

If the color space and format conversion is reported, the <i>SupportedFlags</i> has the <b>D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_SUPPORTED</b> flag set.  

Callers should check the <i>ScaleSupport</i> parameter to understand if the scale is supported.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/C74697BF-A191-4371-9F23-7F655EBC53B3">D3D12DDICAPS_TYPE</a>



<a href="https://msdn.microsoft.com/33BD5E1F-75F3-44DC-AE83-A22992CAB6B5">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/7E272786-ECD4-4DF0-A36A-B27454E3E896">D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS</a>



<a href="https://msdn.microsoft.com/47C0C369-B31B-4291-A420-A1E75BA990CF">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/B9918A06-6C10-4AD7-97EC-4FA0BC5319AD">D3D12DDI_VIDEO_SAMPLE_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/70FFDE9E-2029-4C84-9DEE-C2E81FEE5590">D3D12DDI_VIDEO_SCALE_SUPPORT</a>