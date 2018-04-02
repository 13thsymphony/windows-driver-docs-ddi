---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY
author: windows-driver-content
description: Sets the luma key for an input stream on the video processor.
old-location: display\videoprocessorsetstreamlumakey.htm
old-project: display
ms.assetid: 1b5ca40d-1836-4c80-af55-8d20c6792445
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY, d3d10umddi/pfnVideoProcessorSetStreamLumaKey, display.videoprocessorsetstreamlumakey, pfnVideoProcessorSetStreamLumaKey, pfnVideoProcessorSetStreamLumaKey callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnVideoProcessorSetStreamLumaKey
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY callback function
Sets the luma key for an input stream on the video processor.

## Syntax

```
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMLUMAKEY Pfnd3d111DdiVideoprocessorsetstreamlumakey;

void Pfnd3d111DdiVideoprocessorsetstreamlumakey(
   D3D10DDI_HDEVICE,
   D3D11_1DDI_HVIDEOPROCESSOR,
   UINT,
   BOOL,
   FLOAT,
   FLOAT
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11_1DDI_HVIDEOPROCESSOR`



`UINT`



`BOOL`



`FLOAT`



`FLOAT`




## Return Value

This callback function does not return a value.

## Remarks

The values of <i>Lower</i> and <i>Upper</i> give the lower and upper bounds of the luma key by using a nominal range from zero to one. Given a format with <i>n</i> bits per channel, these values are converted to luma values as follows:

<code>val = f * ((1 &lt;&lt; n)-1)</code>

Any pixel whose luma value falls within the upper and lower bounds (inclusive) is treated as transparent.

For example, if the pixel format uses 8-bit luma, the upper bound is calculated as follows:

<code>BYTE Y = BYTE(max(min(1.0, Upper), 0.0) * 255.0)</code>

Note that the value is clamped to the range from zero to one before multiplying by 255.

The driver reports its ability to support stereo alpha blending for an input stream  in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450968">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY</b> capability, it can be enabled or disabled to set a luma key on an input stream of the video processor.

<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetStreamLumaKey</b> function.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450968">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a>