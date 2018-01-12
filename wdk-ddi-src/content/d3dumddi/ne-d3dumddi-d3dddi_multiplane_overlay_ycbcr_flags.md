---
UID: NE:d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
title: D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
author: windows-driver-content
description: Identifies YUV range and conversion info that describes a multiplane overlay.
old-location: display\d3dddi_multiplane_overlay_ycbcr_flags.htm
old-project: display
ms.assetid: d28170a4-2cf3-4e42-bc76-afdb8c3bce70
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS, D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
req.alt-loc: D3dumddi.h
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
req.typenames: D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS
---

# D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS enumeration



## -description
Identifies YUV range and conversion info that describes a multiplane overlay.



## -syntax

````
typedef enum D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS { 
  D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE  = 0x1,
  D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709          = 0x2,
  D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC          = 0x4
} D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAGS;
````


## -enum-fields

### -field D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_NOMINAL_RANGE

YUV values range from 16 to 235, inclusive, instead of the default range of 0 to 255, inclusive.


### -field D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_BT709

YUV values should be converted using the BT.709 standard, instead of the default BT.601 conversion.


### -field D3DDDI_MULTIPLANE_OVERLAY_YCbCr_FLAG_xvYCC

YUV values contain xvYCC data, instead of conventional YCbCr data.


## -remarks
For more info on how YUV ranges are defined and converted, see <a href="https://msdn.microsoft.com/D76FFB8C-CA42-446E-826F-52982B1849E5">YUV format ranges in Windows 8.1</a>.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>