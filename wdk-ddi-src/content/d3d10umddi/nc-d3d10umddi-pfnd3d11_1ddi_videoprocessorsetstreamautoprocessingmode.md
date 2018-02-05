---
UID : NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE
title : PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE
author : windows-driver-content
description : Enables or disables automatic processing features for an input stream on the video processor.
old-location : display\videoprocessorsetstreamautoprocessingmode.htm
old-project : display
ms.assetid : 85c504e3-46b4-434a-8ab9-5c866eafe05a
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.videoprocessorsetstreamautoprocessingmode, pfnVideoProcessorSetStreamAutoProcessingMode callback function [Display Devices], pfnVideoProcessorSetStreamAutoProcessingMode, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE, d3d10umddi/pfnVideoProcessorSetStreamAutoProcessingMode
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


# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE callback function
Enables or disables automatic processing features for an input stream on the video processor.

## Syntax

```
PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE Pfnd3d111DdiVideoprocessorsetstreamautoprocessingmode;

void Pfnd3d111DdiVideoprocessorsetstreamautoprocessingmode(
   D3D10DDI_HDEVICE,
   D3D11_1DDI_HVIDEOPROCESSOR,
   UINT,
   BOOL
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11_1DDI_HVIDEOPROCESSOR`



`UINT`



`BOOL`




## Return Value

This callback function does not return a value.

## Remarks

By default, the driver might perform certain processing tasks automatically during the video processor bit-block transfer (bitblt). The <b>VideoProcessorSetStreamAutoProcessingMode</b> function enables the application to disable these additional video processing features that the driver may expose. 

For example, if the independent software vendor (ISV) provides its own pixel shader for the video processor, it might want to disable the driver's automatic processing.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md">CreateVideoProcessor</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>