---
UID : NE:d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
title : D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
author : windows-driver-content
description : Identifies YUV range and conversion info that describes a multiplane overlay.
old-location : display\d3dddi_multiplane_overlay_ycbcr_flags.htm
old-project : display
ms.assetid : d28170a4-2cf3-4e42-bc76-afdb8c3bce70
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS, D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
req.alt-loc : D3dumddi.h
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
req.typenames : D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
---

# D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS Enumeration
Identifies YUV range and conversion info that describes a multiplane overlay.

## Syntax
````
typedef enum D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS { 
  D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE  = 0x1,
  D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709          = 0x2,
  D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC          = 0x4
} D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS;
````

## Constants

<table>

<tr>
<td>D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709</td>
<td>YUV values should be converted using the BT.709 standard, instead of the default BT.601 conversion.</td>
</tr>

<tr>
<td>D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE</td>
<td>YUV values range from 16 to 235, inclusive, instead of the default range of 0 to 255, inclusive.</td>
</tr>

<tr>
<td>D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC</td>
<td>YUV values contain xvYCC data, instead of conventional YCbCr data.</td>
</tr>
</table>

## Remarks

For more info on how YUV ranges are defined and converted, see <a href="https://msdn.microsoft.com/D76FFB8C-CA42-446E-826F-52982B1849E5">YUV format ranges in Windows 8.1</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |