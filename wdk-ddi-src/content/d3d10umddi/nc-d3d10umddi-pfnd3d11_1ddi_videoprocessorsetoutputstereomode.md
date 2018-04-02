---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE
author: windows-driver-content
description: Specifies whether the video processor produces stereo video frames.
old-location: display\videoprocessorsetoutputstereomode.htm
old-project: display
ms.assetid: 3e3eaaa6-2725-49de-bca6-df2da1b4324b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE, d3d10umddi/pfnVideoProcessorSetOutputStereoMode, display.videoprocessorsetoutputstereomode, pfnVideoProcessorSetOutputStereoMode, pfnVideoProcessorSetOutputStereoMode callback function [Display Devices]
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
-	pfnVideoProcessorSetOutputStereoMode
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE callback function
Specifies whether the video processor produces stereo video frames.

## Syntax

```
PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTSTEREOMODE Pfnd3d111DdiVideoprocessorsetoutputstereomode;

void Pfnd3d111DdiVideoprocessorsetoutputstereomode(
   D3D10DDI_HDEVICE,
   D3D11_1DDI_HVIDEOPROCESSOR,
   BOOL
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11_1DDI_HVIDEOPROCESSOR`



`BOOL`




## Return Value

This callback function does not return a value.

## Remarks

By default, the video processor produces mono video frames. If stereo video is enabled, the stereo output format is set through the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439817">VideoProcessorSetStreamStereoFormat</a> function.



The driver reports its ability to support stereo video modes through the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> capability, it can be enabled or disabled to produce stereo video frames.

<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetOutputStereoMode</b> function.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/741045a2-0a91-490a-907d-5f4900a4a0ae">CreateVideoProcessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451674">GetVideoProcessorCaps</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439817">VideoProcessorSetStreamStereoFormat</a>