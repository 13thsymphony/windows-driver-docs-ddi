---
UID : NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS
title : DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS
author : windows-driver-content
description : Identifies a flip operation to be performed on an overlay plane.
old-location : display\dxgi_ddi_multiplane_overlay_flags.htm
old-project : display
ms.assetid : 74245a8b-1b52-4336-a744-1aedaca0eef5
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS, DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : dxgiddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS
req.alt-loc : Dxgiddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS
---

# DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS Enumeration
Identifies a flip operation to be performed on an overlay plane.

## Syntax
````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS { 
  DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_VERTICAL_FLIP            = 0x1,
  DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_HORIZONTAL_FLIP          = 0x2,
  DXGI_MULTIPLANE_OVERLAY_FLAG_FULLSCREEN_POST_COMPOSITION  = 0x4
} DXGI_DDI_MULTIPLANE_OVERLAY_FLAGS;
````

## Constants

<table>

<tr>
<td>DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_HORIZONTAL_FLIP</td>
<td>The overlay plane should flip the data horizontally, making it appear as a right-to-left mirror image.</td>
</tr>

<tr>
<td>DXGI_DDI_MULTIPLANE_OVERLAY_FLAG_VERTICAL_FLIP</td>
<td>The overlay plane should flip the data vertically, making it appear upside-down.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dxgiddi.h (include D3d10umddi.h) |