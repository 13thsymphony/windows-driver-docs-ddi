---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE
title: D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE
author: windows-driver-content
description: Specifies the rate at which the video processor produces output frames from an input stream.
old-location: display\d3d11_1ddi_video_processor_output_rate.htm
old-project: display
ms.assetid: ff34c208-9b42-4f72-bb2a-43f3bb44fd68
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE, display.d3d11_1ddi_video_processor_output_rate, D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_NORMAL, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_NORMAL, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE, D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_HALF, D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE enumeration [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_CUSTOM, D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_CUSTOM, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_HALF
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
-	D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE
---

# D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE Enumeration
Specifies the rate at which the video processor produces output frames from an input stream.

## Syntax
````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE { 
  D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_NORMAL  = 0,
  D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_HALF    = 1,
  D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_CUSTOM  = 2
} D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE;
````

## Constants

<table>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_CUSTOM</td>
                    <td>The output is a custom frame rate.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_HALF</td>
                    <td>The output is half the frame rate.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_NORMAL</td>
                    <td>The output is the normal frame rate.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |