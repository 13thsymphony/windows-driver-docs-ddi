---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE
author: windows-driver-content
description: Sets the color space information for the video processor output surface. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorsetoutputshaderusage.htm
old-project: display
ms.assetid: 320618F6-DE98-45D0-8015-DE24689D24D2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE, d3d10umddi/pfnVideoProcessorSetOutputShaderUsage, display.videoprocessorsetoutputshaderusage, pfnVideoProcessorSetOutputShaderUsage, pfnVideoProcessorSetOutputShaderUsage callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnVideoProcessorSetOutputShaderUsage
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE callback function
Sets the color space information for the video processor output surface. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.

## Syntax

```
PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE Pfnd3dwddm20DdiVideoprocessorsetoutputshaderusage;

void Pfnd3dwddm20DdiVideoprocessorsetoutputshaderusage(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  BOOL ShaderUsage
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

`hVideoProcessor`

A handle to the video processor object.

`ShaderUsage`

Indicates whether the output of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a> may be read by Direct3D shaders.

<div class="alert"><b>Note</b>  This will always be <b>TRUE</b> unless multi-plane overlay hardware exists.</div>
<div> </div>


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>