---
UID: NE:d3dkmdt.DXGK_ENGINE_TYPE
title: DXGK_ENGINE_TYPE
author: windows-driver-content
description: Indicates the type of engine on a GPU node. Note the selection rules discussed in Remarks.
old-location: display\dxgk_engine_type.htm
old-project: display
ms.assetid: D94EF91A-784D-4AA2-A43D-6A4AE88CF0A3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_ENGINE_TYPE, DXGK_ENGINE_TYPE enumeration [Display Devices], DXGK_ENGINE_TYPE_3D, DXGK_ENGINE_TYPE_COPY, DXGK_ENGINE_TYPE_OTHER, DXGK_ENGINE_TYPE_OVERLAY, DXGK_ENGINE_TYPE_SCENE_ASSEMBLY, DXGK_ENGINE_TYPE_VIDEO_DECODE, DXGK_ENGINE_TYPE_VIDEO_ENCODE, DXGK_ENGINE_TYPE_VIDEO_PROCESSING, d3dkmdt/DXGK_ENGINE_TYPE, d3dkmdt/DXGK_ENGINE_TYPE_3D, d3dkmdt/DXGK_ENGINE_TYPE_COPY, d3dkmdt/DXGK_ENGINE_TYPE_OTHER, d3dkmdt/DXGK_ENGINE_TYPE_OVERLAY, d3dkmdt/DXGK_ENGINE_TYPE_SCENE_ASSEMBLY, d3dkmdt/DXGK_ENGINE_TYPE_VIDEO_DECODE, d3dkmdt/DXGK_ENGINE_TYPE_VIDEO_ENCODE, d3dkmdt/DXGK_ENGINE_TYPE_VIDEO_PROCESSING, display.dxgk_engine_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	DXGK_ENGINE_TYPE
product: Windows
targetos: Windows
req.typenames: DXGK_ENGINE_TYPE
---

# DXGK_ENGINE_TYPE Enumeration
Indicates the type of engine on a GPU node. Note the selection rules discussed in Remarks.

## Syntax
```
typedef enum DXGK_ENGINE_TYPE {
  DXGK_ENGINE_TYPE_OTHER             ,
  DXGK_ENGINE_TYPE_3D                ,
  DXGK_ENGINE_TYPE_VIDEO_DECODE      ,
  DXGK_ENGINE_TYPE_VIDEO_ENCODE      ,
  DXGK_ENGINE_TYPE_VIDEO_PROCESSING  ,
  DXGK_ENGINE_TYPE_SCENE_ASSEMBLY    ,
  DXGK_ENGINE_TYPE_COPY              ,
  DXGK_ENGINE_TYPE_OVERLAY           ,
  DXGK_ENGINE_TYPE_CRYPTO            ,
  DXGK_ENGINE_TYPE_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>DXGK_ENGINE_TYPE_OTHER</td>
                    <td>The engine does not match any of the other <a href="https://msdn.microsoft.com/library/windows/hardware/dn265417">DXGK_ENGINE_TYPE</a> enumeration values. This value is used for proprietary or unique functionality that is not exposed by typical adapters, as well as for an engine that performs work that doesn't fall under another category.</td>
                </tr>
            
                <tr>
                    <td>DXGK_ENGINE_TYPE_3D</td>
                    <td>The adapter's 3-D processing engine. All adapters that are not a <a href="https://msdn.microsoft.com/584E78DD-5D08-4A20-B59B-F35178F6595C">display-only device</a> have one 3-D engine.</td>
                </tr>
            
                <tr>
                    <td>DXGK_ENGINE_TYPE_VIDEO_DECODE</td>
                    <td>The engine that handles video decoding, including decompression of video frames from an input stream into typical YUV surfaces.

The workload packets for an H.264 video codec workload test must appear on either the decode engine or the 3-D engine.</td>
                </tr>
            
                <tr>
                    <td>DXGK_ENGINE_TYPE_VIDEO_ENCODE</td>
                    <td>The engine that handles video encoding, including compression of typical video frames into an encoded video format.</td>
                </tr>
            
                <tr>
                    <td>DXGK_ENGINE_TYPE_VIDEO_PROCESSING</td>
                    <td>The engine that is responsible for any video processing that is done after a video input stream is decoded. Such processing can include RGB surface conversion, filtering, stretching, color correction, deinterlacing, or other steps that are required before the final image is rendered to the display screen.

The workload packets for workload tests must appear on either the video processing engine or the 3-D engine.</td>
                </tr>
            
                <tr>
                    <td>DXGK_ENGINE_TYPE_SCENE_ASSEMBLY</td>
                    <td>The engine that performs vertex processing of 3-D workloads as a preliminary pass prior to the remainder of the 3-D rendering. This engine also stores vertices in bins that tile-based rendering engines use.</td>
                </tr>
            
                <tr>
                    <td>DXGK_ENGINE_TYPE_COPY</td>
                    <td>The engine that is a copy engine used for moving data. This engine can perform subresource updates, blitting, paging, or other similar data handling.

The workload packets for calls to <b>CopySubresourceRegion</b> or <b>UpdateSubResource</b> methods of Direct3D 10 and Direct3D 11 must appear on either the copy engine or the 3-D engine.</td>
                </tr>
            
                <tr>
                    <td>DXGK_ENGINE_TYPE_OVERLAY</td>
                    <td>The virtual engine that is used for synchronized flipping of overlays in Direct3D 9.</td>
                </tr>
            
                <tr>
                    <td>DXGK_ENGINE_TYPE_CRYPTO</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>DXGK_ENGINE_TYPE_MAX</td>
                    <td></td>
                </tr>
</table>

## Remarks

The display miniport driver should follow these rules to determine the engine type:

<ol>
<li>If the engine performs the adapter's 3-D workloads, the driver must specify only <b>DXGK_ENGINE_TYPE_3D</b>.<div class="alert"><b>Note</b>  The driver must expose exactly one 3-D engine per adapter.</div>
<div> </div>
</li>
<li>If the engine's functionality can be described by any of the <b>DXGK_ENGINE_TYPE</b> enumeration values (except for <b>DXGK_ENGINE_TYPE_OTHER</b>), the driver must select that value.</li>
<li>If more than one <b>DXGK_ENGINE_TYPE</b> enumeration value describes the engine type, the driver should select the one that reflects the dominant capability of that engine. If two capabilities are roughly equal, such as when an engine is used equally for video decode and encode, than the driver can choose either value.</li>
<li>If none of the conditions in steps 1-3 are met, only then should the driver select a value of <b>DXGK_ENGINE_TYPE_OTHER</b>.</li>
</ol>
For more information on how to use this enumeration, see <a href="https://msdn.microsoft.com/822FEB3E-A39D-4B33-BD9D-F3166EF99AF8">Enumerating GPU engine capabilities</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | d3dkmdt.h (include D3dkmddi.h) |