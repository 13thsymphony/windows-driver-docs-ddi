---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_ROTATION
title: D3D11_1DDI_VIDEO_PROCESSOR_ROTATION
author: windows-driver-content
description: Specifies the clockwise rotation of the input stream of the video processor.
old-location: display\d3d11_1ddi_video_processor_rotation.htm
old-project: display
ms.assetid: 4fe01ddd-723f-4b3c-884a-a18d4f8512e5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_ROTATION enumeration [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ROTATION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_90, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_180, D3D11_1DDI_VIDEO_PROCESSOR_ROTATION, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_270, D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_180, d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_IDENTITY, display.d3d11_1ddi_video_processor_rotation, D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_90, D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_IDENTITY, D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_270
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
-	D3D11_1DDI_VIDEO_PROCESSOR_ROTATION
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_ROTATION
---

# D3D11_1DDI_VIDEO_PROCESSOR_ROTATION Enumeration
Specifies the clockwise rotation of the input stream of the video processor.

## Syntax
````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_ROTATION { 
  D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_IDENTITY  = 0,
  D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_90        = 1,
  D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_180       = 2,
  D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_270       = 3
} D3D11_1DDI_VIDEO_PROCESSOR_ROTATION;
````

## Constants

<table>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_180</td>
                    <td>Indicates that rotation is 180 degrees clockwise—inverted landscape mode.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_270</td>
                    <td>Indicates that rotation is 270 degrees clockwise—inverted portrait mode.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_90</td>
                    <td>Indicates that rotation is 90 degrees clockwise—portrait mode.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_IDENTITY</td>
                    <td>Indicates that rotation is 0 degrees—landscape mode.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |