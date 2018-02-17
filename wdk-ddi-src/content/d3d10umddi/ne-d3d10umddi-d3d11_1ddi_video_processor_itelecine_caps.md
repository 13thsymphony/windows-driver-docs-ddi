---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS
author: windows-driver-content
description: Specifies the inverse telecine (IVTC) capabilities of a video processor.
old-location: display\d3d11_1ddi_video_processor_itelecine_caps.htm
old-project: display
ms.assetid: 866203d9-9621-4458-b146-be90e67c1c7c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_22, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_222222222223, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_OTHER, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_32322, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_2224, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_22, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_32, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_87, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_32322, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_55, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_87, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_55, display.d3d11_1ddi_video_processor_itelecine_caps, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_64, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_64, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_OTHER, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_222222222223, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_2224, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_32, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS enumeration [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_2332, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_2332
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
-	D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS Enumeration
Specifies the inverse telecine (IVTC) capabilities of a video processor.

## Syntax
````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS { 
  D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_32            = 0x1,
  D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_22            = 0x2,
  D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_2224          = 0x4,
  D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_2332          = 0x8,
  D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_32322         = 0x10,
  D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_55            = 0x20,
  D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_64            = 0x40,
  D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_87            = 0x80,
  D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_222222222223  = 0x100,
  D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_OTHER         = 0x80000000
} D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS;
````

## Constants

<table>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_22</td>
                    <td>The video processor can reverse 2:2 pulldown.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_222222222223</td>
                    <td>The video processor can reverse 2:2:2:2:2:2:2:2:2:2:2:3 pulldown.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_2224</td>
                    <td>The video processor can reverse 2:2:2:4 pulldown.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_2332</td>
                    <td>The video processor can reverse 2:3:3:2 pulldown.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_32</td>
                    <td>The video processor can reverse 3:2 pulldown.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_32322</td>
                    <td>The video processor can reverse 3:2:3:2:2 pulldown.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_55</td>
                    <td>The video processor can reverse 5:5 pulldown.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_64</td>
                    <td>The video processor can reverse 6:4 pulldown.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_87</td>
                    <td>The video processor can reverse 8:7 pulldown.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_OTHER</td>
                    <td>The video processor can reverse other telecine modes not listed here.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |