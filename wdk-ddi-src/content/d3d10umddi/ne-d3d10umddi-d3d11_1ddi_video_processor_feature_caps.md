---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS
author: windows-driver-content
description: Defines features that a Microsoft Direct3D 11 video processor can support.
old-location: display\d3d11_1ddi_video_processor_feature_caps.htm
old-project: display
ms.assetid: 994f8de8-bb2f-441d-af45-87b9e600ed64
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_SHADER_USAGE, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY, display.d3d11_1ddi_video_processor_feature_caps, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_MIRROR, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_STREAM, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_CONSTRICTION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_MIRROR, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LEGACY, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS enumeration [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ROTATION, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ROTATION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_SHADER_USAGE, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_STREAM, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LEGACY, D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_CONSTRICTION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY, d3d10umddi/
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d10umddi.h
apiname:
-	D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS Enumeration
Defines features that a Microsoft Direct3D 11 video processor can support.

## Syntax
````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS { 
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL          = 0x1,
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_CONSTRICTION        = 0x2,
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY            = 0x4,
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE       = 0x8,
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LEGACY              = 0x10,
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO              = 0x20,
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ROTATION            = 0x40,
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_STREAM        = 0x80,
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO  = 0x100,
#if D3D11DDI_MINOR_HEADER_VERSION >= 5
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_MIRROR              = 0x200,
  D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_SHADER_USAGE  = 0x400,
#endif 
  
} D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS;
````

## Constants

<table>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_FILL</td>
                    <td>The video processor can set alpha values on the output pixels. For more information, see <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md">VideoProcessorSetOutputAlphaFillMode</a>.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_PALETTE</td>
                    <td>The video processor can apply alpha values from color palette entries.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ALPHA_STREAM</td>
                    <td>The video processor supports blending input streams using a per-stream alpha value.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_CONSTRICTION</td>
                    <td>The video processor can downsample the video output. For more information, see <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputconstriction.md">VideoProcessorSetOutputConstriction</a>.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LEGACY</td>
                    <td>The driver does not support the DXVA-HDDDI. If this capability flag is set, the video processor has the following limitations:
<ul>
<li>A maximum of two streams are supported:<ul>
<li>The first stream must be either NV12 or YUY2.</li>
<li>The second stream must be AYUV, AI44, or IA44.</li>
</ul>
</li>
<li>Image adjustment (proc amp) controls are applied to the entire video processing blit, rather than per stream.</li>
<li>Support for per-stream planar alpha is not reliable. (Per-pixel alpha is supported, however.)</li>
</ul></td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_LUMA_KEY</td>
                    <td>The video processor can perform luma keying. For more information, see <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamlumakey.md">VideoProcessorSetStreamLumaKey</a>.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_MIRROR</td>
                    <td>Indicates that the driver supports <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreammirror.md">VideoProcessorSetStreamMirror</a>.

Supported starting with Windows 10.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_PIXEL_ASPECT_RATIO</td>
                    <td>The video processor supports explicit aspect ratios for the source and destination.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_ROTATION</td>
                    <td>The video processor is capable of rotating the input stream by 90, 180, or 270 degrees (clockwise).</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_SHADER_USAGE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</td>
                    <td>The video processor can support 3-D stereo video. For more information, see <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a>.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS_METADATA_HDR10</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

    ## See Also

        <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputalphafillmode.md">VideoProcessorSetOutputAlphaFillMode</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetoutputconstriction.md">VideoProcessorSetOutputConstriction</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamlumakey.md">VideoProcessorSetStreamLumaKey</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videoprocessorsetstreammirror.md">VideoProcessorSetStreamMirror</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>