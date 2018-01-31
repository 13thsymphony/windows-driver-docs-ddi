---
UID : NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT
title : D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT
author : windows-driver-content
description : Specifies the layout in memory of a stereo 3-D video frame.
old-location : display\d3d11_1ddi_video_processor_stereo_format.htm
old-project : display
ms.assetid : 348d17f3-a688-4f63-87aa-a8588f069c5c
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_HORIZONTAL, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT enumeration [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_HORIZONTAL, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT, display.d3d11_1ddi_video_processor_stereo_format, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_VERTICAL, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_VERTICAL, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET, D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
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
req.typenames : D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT
---

# D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT Enumeration
Specifies the layout in memory of a stereo 3-D video frame.

## Syntax
````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT { 
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO                = 0,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_HORIZONTAL          = 1,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_VERTICAL            = 2,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE            = 3,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET         = 4,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED     = 5,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED  = 6,
  D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD        = 7
} D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT;
````

## Constants

<table>

<tr>
<td>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_CHECKERBOARD</td>
<td>Frame 0 and frame 1 are packed in a checkerboard format, as shown in the following diagram.

<img alt="Checkerboard packing" src="images/dxgistereo3d05.png"/>

Support for this stereo format is optional.</td>
</tr>

<tr>
<td>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_COLUMN_INTERLEAVED</td>
<td>Frame 0 and frame 1 are packed into interleaved columns, as shown in the following diagram.

<img alt="Interleaved columns" src="images/dxgistereo3d04.png"/>

Support for this stereo format is optional.</td>
</tr>

<tr>
<td>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_HORIZONTAL</td>
<td>Frame 0 and frame 1 are packed side-by-side, as shown in the following diagram.

<img alt="Side-by-side packing" src="images/dxgistereo3d02.png"/>

All drivers that support stereo video must support this format.</td>
</tr>

<tr>
<td>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO</td>
<td>The sample does not contain stereo data. If the stereo format is not specified, this value is the default.</td>
</tr>

<tr>
<td>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_MONO_OFFSET</td>
<td>The sample contains non-stereo data. However, the driver should create a left/right output of this sample using a specified offset.  The offset is specified in the <i>MonoOffset</i> parameter of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a> function. 

This format is primarily intended for subtitles and other subpicture data, where the entire sample is presented on the same plane.

Support for this stereo format is optional.</td>
</tr>

<tr>
<td>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_ROW_INTERLEAVED</td>
<td>Frame 0 and frame 1 are packed into interleaved rows, as shown in the following diagram.

<img alt="Interleaved rows" src="images/dxgistereo3d03.png"/>

Support for this stereo format is optional.</td>
</tr>

<tr>
<td>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_SEPARATE</td>
<td>Frame 0 and frame 1 are placed in separate resources or in separate texture array elements within the same resource.

All drivers that support stereo video must support this format.</td>
</tr>

<tr>
<td>D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT_VERTICAL</td>
<td>Frame 0 and frame 1 are packed top-to-bottom, as shown in the following diagram.

<img alt="Top-to-bottom packing" src="images/dxgistereo3d01.png"/>

All drivers that support stereo video must support this format.</td>
</tr>
</table>

## Remarks

This enumeration designates the two stereo views as "frame 0" and "frame 1". The <i>LeftViewFrame0</i> parameter of the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a> method specifies which view is the left view, and which is the right view.

For packed formats, if the source rectangle clips part of the surface, the driver interprets the rectangle in logical coordinates relative to the stereo view,  rather than absolute pixel coordinates. The result is that frame 0 and frame 1 are clipped proportionately.

To query whether the device supports stereo 3-D video, call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a> and check for the <b>D3D11_VIDEO_PROCESSOR_FEATURE_CAPS_STEREO</b> flag in the <b>FeatureCaps</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure. If this capability flag is present, it means that the driver supports all of the stereo formats that are not  listed as optional. To find out which optional formats are supported, call <b>GetVideoProcessorCaps</b> and check the <b>StereoCaps</b> member of the structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamstereoformat.md">VideoProcessorSetStreamStereoFormat</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps.md">GetVideoProcessorCaps</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDI_VIDEO_PROCESSOR_STEREO_FORMAT enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>