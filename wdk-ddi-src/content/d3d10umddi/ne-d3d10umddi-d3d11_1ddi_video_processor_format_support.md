---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT
title: D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT
author: windows-driver-content
description: Specifies how a video format can be used for video processing.
old-location: display\d3d11_1ddi_video_processor_format_support.htm
old-project: display
ms.assetid: 3fef0cb0-6584-487d-9660-1c748509a6a9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT, D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT enumeration [Display Devices], D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT_INPUT, D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT_OUTPUT, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT_INPUT, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT_OUTPUT, display.d3d11_1ddi_video_processor_format_support
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT
---

# D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT Enumeration
Specifies how a video format can be used for video processing.

## Syntax
```
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT {
  D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT_INPUT   ,
  D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT_OUTPUT
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT_INPUT</td>
                    <td>The format can be used as the input to the video processor.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_SUPPORT_OUTPUT</td>
                    <td>The format can be used as the output from the video processor.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |