---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_INPUT
title: D3D11_1DDI_VIDEO_INPUT
author: windows-driver-content
description: Reserved for system use. Do not use in your driver.
old-location: display\d3d11_1ddi_video_input.htm
old-project: display
ms.assetid: 371f494c-abd2-43c8-ab06-749144762b01
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_VIDEO_INPUT, D3D11_1DDI_VIDEO_INPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_INPUT, display.d3d11_1ddi_video_input
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
-	D3D11_1DDI_VIDEO_INPUT
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_VIDEO_INPUT
---

# D3D11_1DDI_VIDEO_INPUT structure
Reserved for system use. Do not use in your driver.

## Syntax
````
typedef struct D3D11_1DDI_VIDEO_INPUT {
  BOOL                        Relocate;
  D3D11_1DDI_VIDEODEVICEFUNCS *p11VideoDeviceFuncs;
} D3D11_1DDI_VIDEO_INPUT;
````

## Members


`Relocate`

Reserved for system use. Do not use in your driver.

`p11VideoDeviceFuncs`

Reserved for system use. Do not use in your driver.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |