---
UID: NC:d3d10umddi.PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT
title: PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT
author: windows-driver-content
description: Queries whether the video processor supports a specified video format.
old-location: display\checkvideoprocessorformat.htm
old-project: display
ms.assetid: f5f18a53-d121-445a-86b7-649624a2f175
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CheckVideoProcessorFormat, CheckVideoProcessorFormat callback function [Display Devices], PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT, d3d10umddi/CheckVideoProcessorFormat, display.checkvideoprocessorformat
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
-	CheckVideoProcessorFormat
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT callback function
Queries whether the video processor supports a specified video format.

## Syntax

```
PFND3D11_1DDI_CHECKVIDEOPROCESSORFORMAT Pfnd3d111DdiCheckvideoprocessorformat;

void Pfnd3d111DdiCheckvideoprocessorformat(
   D3D10DDI_HDEVICE,
   D3D11_1DDI_HVIDEOPROCESSORENUM,
   DXGI_FORMAT,
  UINT *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11_1DDI_HVIDEOPROCESSORENUM`



`DXGI_FORMAT`



`*`




## Return Value

This callback function does not return a value.

## Remarks

If the driver can support the format as an input format for the video processor, the driver sets the <b>D3D11_1DDI_VIDEO_FORMAT_SUPPORT_VIDEO_PROCESSOR_INPUT</b> flag in the <i>pSupported</i> parameter.



If the driver can support the format as a video processing render target output format, the driver sets the <b>D3D11_1DDI_VIDEO_FORMAT_SUPPORT_VIDEO_PROCESSOR_OUTPUT</b> flag in the <i>pSupported</i> parameter.



If the driver can support neither, it must set the <i>pSupported</i> parameter to 0.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1ddi_video_processor_format_support.md">D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum.md">CreateVideoProcessorEnum</a>