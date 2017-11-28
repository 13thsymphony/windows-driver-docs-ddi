---
UID: NS.d3dhal._D3DHAL_DP2SETCLIPPLANE
title: D3DHAL_DP2SETCLIPPLANE
author: windows-driver-content
description: The D3DHAL_SETCLIPPLANE structure allows user defined clip planes to be used in world space.
old-location: display\d3dhal_dp2setclipplane.htm
old-project: display
ms.assetid: 84459f39-42cb-4877-b569-17c51ee2d6e4
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2SETCLIPPLANE, D3DHAL_DP2SETCLIPPLANE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DHAL_DP2SETCLIPPLANE
req.alt-loc: d3dhal.h
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
req.iface: 
---

# D3DHAL_DP2SETCLIPPLANE structure



## -description
<p>The D3DHAL_SETCLIPPLANE structure allows user defined clip planes to be used in world space.</p>


## -syntax

````
typedef struct _D3DHAL_DP2SETCLIPPLANE {
  DWORD    dwIndex;
  D3DVALUE plane[4];
} D3DHAL_DP2SETCLIPPLANE, *LPD3DHAL_DP2SETCLIPPLANE;
````


## -struct-fields
<dl>

### -field <b>dwIndex</b>

<dd>
<p>Specifies the index of the clipping plane for which the plane equation coefficients will be set.</p>
</dd>

### -field <b>plane</b>

<dd>
<p>Specifies a four-element array of the coefficients A, B, C, and D, in that order, in the general plane equation for the clipping plane. </p>
</dd>
</dl>

## -remarks
<p>The general plane equation in standard form is A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i>  = 0. A point with homogeneous coordinates (<i>x</i>, <i>y</i>, <i>z</i>, <i>w</i>) is visible in the half-space of this plane if A<i>x</i> + B<i>y</i> + C<i>z</i> + D<i>w</i>  &gt;= 0. Points that exist on or behind the clipping plane are clipped from the scene. That is, points for which Ax + By + Cz + Dw &lt;= 0 are clipped.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dhal.h (include D3dhal.h)</dt>
</dl>
</td>
</tr>
</table>