---
UID: NE.dxgiddi.DXGI_DDI_MODE_SCANLINE_ORDER
title: DXGI_DDI_MODE_SCANLINE_ORDER
author: windows-driver-content
description: The DXGI_DDI_MODE_SCANLINE_ORDER enumeration type contains values that identify how scan lines are ordered in a display mode.
old-location: display\dxgi_ddi_mode_scanline_order.htm
old-project: display
ms.assetid: 114a6f0d-22ec-4306-81b4-56cf882f167f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: DXGI_DDI_MODE_SCANLINE_ORDER, DXGI_DDI_MODE_SCANLINE_ORDER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_MODE_SCANLINE_ORDER
req.alt-loc: dxgiddi.h
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

# DXGI_DDI_MODE_SCANLINE_ORDER enumeration



## -description
The DXGI_DDI_MODE_SCANLINE_ORDER enumeration type contains values that identify how scan lines are ordered in a display mode.


## -syntax

````
typedef enum DXGI_DDI_MODE_SCANLINE_ORDER { 
  DXGI_DDI_MODE_SCANLINE_ORDER_UNSPECIFIED        = 0,
  DXGI_DDI_MODE_SCANLINE_ORDER_PROGRESSIVE        = 1,
  DXGI_DDI_MODE_SCANLINE_ORDER_UPPER_FIELD_FIRST  = 2,
  DXGI_DDI_MODE_SCANLINE_ORDER_LOWER_FIELD_FIRST  = 3
} DXGI_DDI_MODE_SCANLINE_ORDER;
````


## -enum-fields

### -field DXGI_DDI_MODE_SCANLINE_ORDER_UNSPECIFIED

A DXGI_DDI_MODE_SCANLINE_ORDER-typed variable has not yet been assigned a meaningful value.

### -field DXGI_DDI_MODE_SCANLINE_ORDER_PROGRESSIVE

Each field contains an entire frame.

### -field DXGI_DDI_MODE_SCANLINE_ORDER_UPPER_FIELD_FIRST

Each field contains half of a frame, and the odd scan lines are displayed first.

### -field DXGI_DDI_MODE_SCANLINE_ORDER_LOWER_FIELD_FIRST

Each field contains half of a frame, and the even scan lines are displayed first.

## -remarks
The values of the DXGI_DDI_MODE_SCANLINE_ORDER enumeration type indicate whether the image that is displayed on the monitor contains the entire content of a video frame or only half of the content (that is, either the even or odd scan lines, which occur interchangeably). The values also indicate which field comes first in the order.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_mode_desc.md">DXGI_DDI_MODE_DESC</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_MODE_SCANLINE_ORDER enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
