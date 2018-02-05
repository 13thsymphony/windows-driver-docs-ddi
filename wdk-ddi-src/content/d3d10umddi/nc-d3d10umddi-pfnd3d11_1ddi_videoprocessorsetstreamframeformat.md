---
UID : NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT
title : PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT
author : windows-driver-content
description : Specifies whether an input stream on the video processor contains interlaced or progressive frames.
old-location : display\videoprocessorsetstreamframeformat.htm
old-project : display
ms.assetid : 49310ddf-403a-4fb4-98bb-9ef00ef28310
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.videoprocessorsetstreamframeformat, pfnVideoProcessorSetStreamFrameFormat callback function [Display Devices], pfnVideoProcessorSetStreamFrameFormat, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT, d3d10umddi/pfnVideoProcessorSetStreamFrameFormat
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


# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT callback function
Specifies whether an input stream on the video processor contains interlaced or progressive frames.

## Syntax

```
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT Pfnd3d111DdiVideoprocessorsetstreamframeformat;

void Pfnd3d111DdiVideoprocessorsetstreamframeformat(
   D3D10DDI_HDEVICE,
   D3D11_1DDI_HVIDEOPROCESSOR,
   UINT,
   D3D11_1DDI_VIDEO_FRAME_FORMAT
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11_1DDI_HVIDEOPROCESSOR`



`UINT`



`D3D11_1DDI_VIDEO_FRAME_FORMAT`




## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_frame_format.md">D3D11_1DDI_VIDEO_FRAME_FORMAT</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFRAMEFORMAT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>