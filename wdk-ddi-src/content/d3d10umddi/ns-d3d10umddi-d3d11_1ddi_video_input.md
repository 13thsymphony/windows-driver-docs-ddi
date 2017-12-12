---
UID: NS.D3D10UMDDI.D3D11_1DDI_VIDEO_INPUT
title: D3D11_1DDI_VIDEO_INPUT
author: windows-driver-content
description: Reserved for system use. Do not use in your driver.
old-location: display\d3d11_1ddi_video_input.htm
old-project: display
ms.assetid: 371f494c-abd2-43c8-ab06-749144762b01
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D11_1DDI_VIDEO_INPUT, D3D11_1DDI_VIDEO_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_VIDEO_INPUT
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

# D3D11_1DDI_VIDEO_INPUT structure



## -description
Reserved for system use. Do not use in your driver.



## -syntax

````
typedef struct D3D11_1DDI_VIDEO_INPUT {
  BOOL                        Relocate;
  D3D11_1DDI_VIDEODEVICEFUNCS *p11VideoDeviceFuncs;
} D3D11_1DDI_VIDEO_INPUT;
````


## -struct-fields

### -field Relocate

Reserved for system use. Do not use in your driver.


### -field p11VideoDeviceFuncs

Reserved for system use. Do not use in your driver.


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