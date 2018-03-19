---
UID: NS:d3dumddi._DXVAHDDDI_SURFACE
title: "_DXVAHDDDI_SURFACE"
author: windows-driver-content
description: The DXVAHDDDI_SURFACE structure describes a surface.
old-location: display\dxvahdddi_surface.htm
old-project: display
ms.assetid: a0bfc9bf-777e-4da4-9414-856ec650375d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA2_Structs_8032b044-07e9-4bb7-9367-1c3283bbf145.xml, DXVAHDDDI_SURFACE, DXVAHDDDI_SURFACE structure [Display Devices], _DXVAHDDDI_SURFACE, d3dumddi/DXVAHDDDI_SURFACE, display.dxvahdddi_surface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_SURFACE is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
api_name:
-	DXVAHDDDI_SURFACE
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_SURFACE
---

# _DXVAHDDDI_SURFACE structure
The DXVAHDDDI_SURFACE structure describes a surface.

## Syntax
````
typedef struct _DXVAHDDDI_SURFACE {
  HANDLE hResource;
  UINT   SubResourceIndex;
} DXVAHDDDI_SURFACE;
````

## Members


`hResource`

[in] A handle to the resource that contains the surface.

`SubResourceIndex`

[in] The zero-based index into the resource, which the handle in the <b>hResource</b> member specifies. The <b>SubResourceIndex</b> index indicates the surface.

## Remarks
DXVAHDDDI_SURFACE structures are used to describe surfaces in members of the <a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_data.md">DXVAHDDDI_STREAM_DATA</a> and <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_videoprocessblthd.md">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a> structures in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_videoprocessblthd.md">VideoProcessBltHD</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | DXVAHDDDI_SURFACE is supported beginning with the Windows 7 operating system. DXVAHDDDI_SURFACE is supported beginning with the Windows 7 operating system. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_dxvahdddi_stream_data.md">DXVAHDDDI_STREAM_DATA</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_videoprocessblthd.md">VideoProcessBltHD</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_dxvahd_videoprocessblthd.md">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a>