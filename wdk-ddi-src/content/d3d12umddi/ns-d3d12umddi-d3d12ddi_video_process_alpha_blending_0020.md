---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020
title: D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020
author: windows-driver-content
description: Specifies whether alpha blending is enabled and, if so, the planar alpha value.
old-location: display\d3d12ddi_video_process_alpha_blending.htm
old-project: display
ms.assetid: 58E7A600-1CA9-40F8-8F37-CA7A0834B3F4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020, D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020, display.d3d12ddi_video_process_alpha_blending
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020
---

# D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020 structure
Specifies whether alpha blending is enabled and, if so, the planar alpha value.

## Syntax
````
typedef struct D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020 {
  BOOL  Enable;
  FLOAT Alpha;
} D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020;
````

## Members


`Alpha`

The planar alpha value. The value can range from 0.0 (transparent) to 1.0 (opaque). If the <b>Enable</b> member is false, this value is ignored.

`Enable`

Specifies whether alpha blending is enabled.

## Remarks
For each pixel, the destination color value is computed as the following: <pre class="syntax" xml:space="preserve"><code>Cd = Cs * (As * Ap * Ae) + Cd * (1.0 - As * Ap * Ae)</code></pre>


The variables in this equation are as follows:

<ul>
<li>
Cd. The color value of the destination pixel.

</li>
<li>
Cs. The color value of the source pixel.

</li>
<li>
As. The per-pixel source alpha.

</li>
<li>
Ap. The planar alpha value.

</li>
<li>
Ae. The palette-entry alpha value, or 1.0.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |