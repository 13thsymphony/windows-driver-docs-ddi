---
UID : NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS
title : PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS
author : windows-driver-content
description : Returns driver hints as to which video processor operations are best performed using multi-plane overlay hardware rather than VideoProcessorBlt. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location : display\videoprocessorgetbehaviorhints.htm
old-project : display
ms.assetid : E6CBAFEE-9587-45D5-A6CD-4CA739AF279E
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.videoprocessorgetbehaviorhints, pfnVideoProcessorGetBehaviorHints callback function [Display Devices], pfnVideoProcessorGetBehaviorHints, PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS, PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS, d3d10umddi/pfnVideoProcessorGetBehaviorHints
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
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
req.typenames : SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS callback function
Returns driver hints as to which video processor operations are best performed using multi-plane overlay hardware rather than <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.

## Syntax

```
PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS Pfnd3dwddm20DdiVideoprocessorgetbehaviorhints;

HRESULT Pfnd3dwddm20DdiVideoprocessorgetbehaviorhints(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  UINT OutputWidth,
  UINT OutputHeight,
  DXGI_FORMAT OutputFormat,
  UINT StreamCount,
  const D3DWDDM2_0DDI_VIDEO_PROCESSOR_STREAM_BEHAVIOR_HINT *pStreams,
  UINT *pBehaviorHints
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

`hVideoProcessor`

Handle to the video processor object.

`OutputWidth`

Indicates the width of the output surface.

`OutputHeight`

Indicates the height of the output surface.

`OutputFormat`

Indicates the output format of the video processor.

`StreamCount`

The number of input streams to process.

`*pStreams`



`*pBehaviorHints`




## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

This function uses the current state, set via the <b>VideoProcessorSetOutput</b> and <b>VideoProcessorSetStream</b> set of  device driver interfaces (DDIs), and returns which operations could be performed more efficiently using multiple overlay hardware.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_VIDEOPROCESSORGETBEHAVIORHINTS callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>