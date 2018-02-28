---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE
author: windows-driver-content
description: Sets the output color space for the video processor.
old-location: display\videoprocessorsetoutputcolorspace.htm
old-project: display
ms.assetid: a6d1020d-e8e1-465f-a133-59afdfe1cfce
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE, d3d10umddi/pfnVideoProcessorSetOutputColorSpace, display.videoprocessorsetoutputcolorspace, pfnVideoProcessorSetOutputColorSpace, pfnVideoProcessorSetOutputColorSpace callback function [Display Devices]
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
-	pfnVideoProcessorSetOutputColorSpace
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE callback function
Sets the output color space for the video processor.

## Syntax

```
PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE Pfnd3d111DdiVideoprocessorsetoutputcolorspace;

void Pfnd3d111DdiVideoprocessorsetoutputcolorspace(
   D3D10DDI_HDEVICE,
   D3D11_1DDI_HVIDEOPROCESSOR,
  CONST D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11_1DDI_HVIDEOPROCESSOR`



`*`




## Return Value

This callback function does not return a value.

## Remarks

The <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_color_space.md">D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE</a> structure includes the following members:

<ul>
<li>
The <b>Usage</b> member specifies whether the output is intended for playback or video processing, such as editing or authoring. The driver can optimize the video processing based on the specified usage. 

</li>
<li>
The <b>RGB_Range</b> member specifies the RGB color range. If this member is set to zero, the transfer matrix is based on the . If this member is set to one, the RGB range is limited to index values from 16 to 235.

</li>
<li>
The <b>YCbCr_Matrix </b> member specifies the YCbCr transfer matrix. If this member is set to zero, the transfer matrix is based on the BT.601 format. If this member is set to one, the transfer matrix is based on the BT.709 format.

<div class="alert"><b>Note</b>  Both of these transfer matrixes define the black point as index 16 and the white point as index 235.</div>
<div> </div>
</li>
<li>
The <b>YCbCr_xvYCC </b> member specifies whether the output uses the conventional YCbCr format or the extended YCbCr (xvYCC) format. 

If this member is set to zero, the format that is used is the conventional YCbCr format. 

If this member is set to one, the format that is used is the extended xvYCC format.

<div class="alert"><b>Note</b>  The xvYCC format can be used with either YCbCr transfer matrix and also defines the black point as index 16 and the white point as index 235. However, the xvYCC format supports blacker luminance values in the range from 1 to 15. The xvYCC format also supports whiter luminance values in the range from 236 to 254.  Therefore, the graphics adapter must not adjust these luminance values to the standard 16 and 235 index values for the white and black point respectively.</div>
<div> </div>
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_color_space.md">D3D11_1DDI_VIDEO_PROCESSOR_COLOR_SPACE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>