---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
title: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
author: windows-driver-content
description: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION is used with CheckVideoProcessorFormatConversion to indicate whether the driver supports a specific format/color space conversion combination.
old-location: display\d3dwddm2_0ddi_check_video_processor_format_conversion.htm
old-project: display
ms.assetid: 3259CEB7-E902-4040-B99E-D0609935E804
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION, D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION, display.d3dwddm2_0ddi_check_video_processor_format_conversion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	D3d10umddi.h
api_name:
-	D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
---

# D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION structure
<b>D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION</b> is used with <a href="https://msdn.microsoft.com/library/windows/hardware/dn906317">CheckVideoProcessorFormatConversion</a> to indicate whether the driver supports a specific format/color space conversion combination.

## Syntax
```
typedef struct D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION {
  DXGI_FORMAT             InputFormat;
  D3DDDI_COLOR_SPACE_TYPE InputColorSpace;
  DXGI_FORMAT             OutputFormat;
  D3DDDI_COLOR_SPACE_TYPE OutputColorSpace;
  BOOL                    Supported;
};
```

## Members


`InputFormat`

Indicates the format of the video processor input.

`InputColorSpace`

Indicates the colorspace of the video processor input.

`OutputFormat`

Indicates the format of the video processor output.

`OutputColorSpace`

Indicates the colorspace of the video processor output.

`Supported`

The driver sets this to <b>TRUE</b> if the conversion between the input format/color space and the output format/color space is supported.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn906317">CheckVideoProcessorFormatConversion</a>