---
UID : NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA
title : PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA
author : windows-driver-content
description : Sets the planar alpha for an input stream on the video processor.
old-location : display\videoprocessorsetstreamalpha.htm
old-project : display
ms.assetid : 9208bcd7-c030-4c2f-b3bc-e1bff3839cef
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.videoprocessorsetstreamalpha, pfnVideoProcessorSetStreamAlpha callback function [Display Devices], pfnVideoProcessorSetStreamAlpha, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA, d3d10umddi/pfnVideoProcessorSetStreamAlpha
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA callback function
Sets the planar alpha for an input stream on the video processor.

## Syntax

```
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA Pfnd3d111DdiVideoprocessorsetstreamalpha;

void Pfnd3d111DdiVideoprocessorsetstreamalpha(
   D3D10DDI_HDEVICE,
   D3D11_1DDI_HVIDEOPROCESSOR,
   UINT,
   BOOL,
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




## Return Value

This callback function does not return a value.

## Remarks

By default, alpha blending is disabled. 



For each pixel, the destination color value is computed as follows:

<code>Cd = Cs * (As * Ap * Ae) + Cd * (1.0 - As * Ap * Ae)</code>

where:
<ul>
<li><code>Cd</code> = The color value of the destination pixel</li>
<li><code>Cs</code> = The color value of the source pixel</li>
<li><code>As</code> = The per-pixel source alpha</li>
<li><code>Ap</code> = The planar alpha value</li>
<li><code>Ae</code> = The palette-entry alpha value, or 1.0 </li>
</ul><div class="alert"><b>Note</b>  Palette-entry alpha values apply only to palettized color formats, and only when the device advertises support for the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE</b> capability through the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> function. Otherwise, this factor equals 1.0.</div><div> </div>The destination alpha value is computed according to the alpha fill mode. For more information, see <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md">VideoProcessorSetOutputAlphaFillMode</a>


The driver reports its ability to support stereo alpha blending for an input stream in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that is returned through the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> function. If the driver supports the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_STREAM </b> capability, it can be enabled or disabled to produce stereo video frames.
<div class="alert"><b>Note</b>  If the driver does not support the <b>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> capability, the Microsoft Direct3D runtime does not call the <b>VideoProcessorSetStreamAlpha</b> function.</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md">VideoProcessorSetOutputAlphaFillMode</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMALPHA callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>