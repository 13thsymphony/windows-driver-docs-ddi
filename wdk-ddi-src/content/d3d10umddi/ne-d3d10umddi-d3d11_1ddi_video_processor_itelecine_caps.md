---
UID: NE.d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS
author: windows-driver-content
description: Specifies the inverse telecine (IVTC) capabilities of a video processor.
old-location: display\d3d11_1ddi_video_processor_itelecine_caps.htm
old-project: display
ms.assetid: 866203d9-9621-4458-b146-be90e67c1c7c
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS
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
req.alt-api: D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS
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

# D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS enumeration



## -description
Specifies the inverse telecine (IVTC) capabilities of a video processor.



## -syntax

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


## -enum-fields

### -field D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_32

The video processor can reverse 3:2 pulldown.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_22

The video processor can reverse 2:2 pulldown.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_2224

The video processor can reverse 2:2:2:4 pulldown.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_2332

The video processor can reverse 2:3:3:2 pulldown.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_32322

The video processor can reverse 3:2:3:2:2 pulldown.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_55

The video processor can reverse 5:5 pulldown.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_64

The video processor can reverse 6:4 pulldown.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_87

The video processor can reverse 8:7 pulldown.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_222222222223

The video processor can reverse 2:2:2:2:2:2:2:2:2:2:2:3 pulldown.


### -field D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS_OTHER

The video processor can reverse other telecine modes not listed here.


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