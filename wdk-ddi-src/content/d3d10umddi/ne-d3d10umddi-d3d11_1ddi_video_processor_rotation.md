---
UID: NE.d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_ROTATION
title: D3D11_1DDI_VIDEO_PROCESSOR_ROTATION
author: windows-driver-content
description: Specifies the clockwise rotation of the input stream of the video processor.
old-location: display\d3d11_1ddi_video_processor_rotation.htm
old-project: display
ms.assetid: 4fe01ddd-723f-4b3c-884a-a18d4f8512e5
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_ROTATION, D3D11_1DDI_VIDEO_PROCESSOR_ROTATION
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
req.alt-api: D3D11_1DDI_VIDEO_PROCESSOR_ROTATION
req.alt-loc: D3d10umddi.h
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
---

# D3D11_1DDI_VIDEO_PROCESSOR_ROTATION enumeration



## -description
Specifies the clockwise rotation of the input stream of the video processor.



## -syntax

````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_ROTATION { 
  D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_IDENTITY  = 0,
  D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_90        = 1,
  D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_180       = 2,
  D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_270       = 3
} D3D11_1DDI_VIDEO_PROCESSOR_ROTATION;
````


## -enum-fields

### -field D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_IDENTITY

Indicates that rotation is 0 degrees—landscape mode.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_90

Indicates that rotation is 90 degrees clockwise—portrait mode.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_180

Indicates that rotation is 180 degrees clockwise—inverted landscape mode.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ROTATION_270

Indicates that rotation is 270 degrees clockwise—inverted portrait mode.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>