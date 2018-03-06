---
UID: NE:d3dkmdt._DXGK_RENDER_PIPELINE_STAGE
title: "_DXGK_RENDER_PIPELINE_STAGE"
author: windows-driver-content
description: The DXGK_RENDER_PIPELINE_STAGE enumeration describes the render pipeline stage during which the GPU error has occurred.
old-location: display\dxgk_render_pipeline_stage.htm
old-project: display
ms.assetid: A6E6439A-8151-4953-B78A-3141A9EA59F2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_RENDER_PIPELINE_STAGE, DXGK_RENDER_PIPELINE_STAGE enumeration [Display Devices], DXGK_RENDER_PIPELINE_STAGE_GEOMETRY_SHADER, DXGK_RENDER_PIPELINE_STAGE_INPUT_ASSEMBLER, DXGK_RENDER_PIPELINE_STAGE_OUTPUT_MERGER, DXGK_RENDER_PIPELINE_STAGE_PIXEL_SHADER, DXGK_RENDER_PIPELINE_STAGE_RASTERIZER, DXGK_RENDER_PIPELINE_STAGE_STREAM_OUTPUT, DXGK_RENDER_PIPELINE_STAGE_UNKNOWN, DXGK_RENDER_PIPELINE_STAGE_VERTEX_SHADER, _DXGK_RENDER_PIPELINE_STAGE, d3dkmdt/DXGK_RENDER_PIPELINE_STAGE, d3dkmdt/DXGK_RENDER_PIPELINE_STAGE_GEOMETRY_SHADER, d3dkmdt/DXGK_RENDER_PIPELINE_STAGE_INPUT_ASSEMBLER, d3dkmdt/DXGK_RENDER_PIPELINE_STAGE_OUTPUT_MERGER, d3dkmdt/DXGK_RENDER_PIPELINE_STAGE_PIXEL_SHADER, d3dkmdt/DXGK_RENDER_PIPELINE_STAGE_RASTERIZER, d3dkmdt/DXGK_RENDER_PIPELINE_STAGE_STREAM_OUTPUT, d3dkmdt/DXGK_RENDER_PIPELINE_STAGE_UNKNOWN, d3dkmdt/DXGK_RENDER_PIPELINE_STAGE_VERTEX_SHADER, display.dxgk_render_pipeline_stage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmdt.h
api_name:
-	DXGK_RENDER_PIPELINE_STAGE
product: Windows
targetos: Windows
req.typenames: DXGK_RENDER_PIPELINE_STAGE
---

# _DXGK_RENDER_PIPELINE_STAGE Enumeration
The <b>DXGK_RENDER_PIPELINE_STAGE</b> enumeration describes the render pipeline stage during which the GPU error has occurred.

## Syntax
````
typedef enum _DXGK_RENDER_PIPELINE_STAGE { 
  DXGK_RENDER_PIPELINE_STAGE_UNKNOWN          = 0,
  DXGK_RENDER_PIPELINE_STAGE_INPUT_ASSEMBLER  = 1,
  DXGK_RENDER_PIPELINE_STAGE_VERTEX_SHADER    = 2,
  DXGK_RENDER_PIPELINE_STAGE_GEOMETRY_SHADER  = 3,
  DXGK_RENDER_PIPELINE_STAGE_STREAM_OUTPUT    = 4,
  DXGK_RENDER_PIPELINE_STAGE_RASTERIZER       = 5,
  DXGK_RENDER_PIPELINE_STAGE_PIXEL_SHADER     = 6,
  DXGK_RENDER_PIPELINE_STAGE_OUTPUT_MERGER    = 7
} DXGK_RENDER_PIPELINE_STAGE;
````

## Constants

<table>
            
                <tr>
                    <td>DXGK_RENDER_PIPELINE_STAGE_GEOMETRY_SHADER</td>
                    <td>Indicates that the error occurred at the geometry shader stage.</td>
                </tr>
            
                <tr>
                    <td>DXGK_RENDER_PIPELINE_STAGE_INPUT_ASSEMBLER</td>
                    <td>Indicates that the error occurred at the input assembler stage.</td>
                </tr>
            
                <tr>
                    <td>DXGK_RENDER_PIPELINE_STAGE_OUTPUT_MERGER</td>
                    <td>Indicates that the error occurred at the output merger stage.</td>
                </tr>
            
                <tr>
                    <td>DXGK_RENDER_PIPELINE_STAGE_PIXEL_SHADER</td>
                    <td>Indicates that the error occurred at the pixel shader stage.</td>
                </tr>
            
                <tr>
                    <td>DXGK_RENDER_PIPELINE_STAGE_RASTERIZER</td>
                    <td>Indicates that the error occurred at the rasterizer stage.</td>
                </tr>
            
                <tr>
                    <td>DXGK_RENDER_PIPELINE_STAGE_STREAM_OUTPUT</td>
                    <td>Indicates that the error occurred at the stream output stage.</td>
                </tr>
            
                <tr>
                    <td>DXGK_RENDER_PIPELINE_STAGE_UNKNOWN</td>
                    <td>Indicates that the stage where the error occurred is unknown.</td>
                </tr>
            
                <tr>
                    <td>DXGK_RENDER_PIPELINE_STAGE_VERTEX_SHADER</td>
                    <td>Indicates that the error occurred at the vertex shader stage.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmdt.h (include D3dkmddi.h) |