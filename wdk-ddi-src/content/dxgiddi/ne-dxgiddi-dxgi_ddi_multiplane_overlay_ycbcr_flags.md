---
UID : NE:dxgiddi.DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
title : DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
author : windows-driver-content
description : Identifies YUV range and conversion info that describes a multiplane overlay.
old-location : display\dxgi_ddi_multiplane_overlay_ycbcr_flags.htm
old-project : display
ms.assetid : fa915ec0-167f-441c-b2de-0ae2b852c432
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE, dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS, display.dxgi_ddi_multiplane_overlay_ycbcr_flags, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS enumeration [Display Devices], dxgiddi/DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709, DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
---

# DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS Enumeration
Identifies YUV range and conversion info that describes a multiplane overlay.

## Syntax
````
typedef enum DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS { 
  DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE  = 0x1,
  DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709          = 0x2,
  DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC          = 0x4
} DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS;
````

## Constants

<table>

<tr>
<td>DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709</td>
<td>YUV values should be converted using the BT.709 standard, instead of the default BT.601 conversion.</td>
</tr>

<tr>
<td>DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE</td>
<td>YUV values range from 16 to 235, inclusive, instead of the default range of 0 to 255, inclusive.</td>
</tr>

<tr>
<td>DXGI_DDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC</td>
<td>YUV values contain xvYCC data, instead of conventional YCbCr data.</td>
</tr>
</table>

## Remarks

For more info on how YUV ranges are defined and converted, see <a href="https://msdn.microsoft.com/D76FFB8C-CA42-446E-826F-52982B1849E5">YUV format ranges in Windows 8.1</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dxgiddi.h (include D3d10umddi.h) |