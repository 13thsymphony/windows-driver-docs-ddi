---
UID: NS:d3dkmddi._DXGK_GDIARG_BITBLT
title: _DXGK_GDIARG_BITBLT
author: windows-driver-content
description: The DXGK_GDIARG_BITBLT structure describes the characteristics of a GDI hardware-accelerated bit-block transfer (bitblt) with no stretching.
old-location: display\dxgk_gdiarg_bitblt.htm
old-project: display
ms.assetid: 367ee4cb-5074-478d-8836-962f96acf103
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GDIARG_BITBLT, DXGK_GDIARG_BITBLT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_GDIARG_BITBLT
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DXGK_GDIARG_BITBLT
---

# _DXGK_GDIARG_BITBLT structure



## -description
The DXGK_GDIARG_BITBLT structure describes the characteristics of a GDI hardware-accelerated <a href="wdkgloss.b#wdkgloss.bit_block_transfer#wdkgloss.bit_block_transfer"><i>bit-block transfer (bitblt)</i></a> with no stretching.



## -syntax

````
typedef struct _DXGK_GDIARG_BITBLT {
  RECT SrcRect;
  RECT DstRect;
  UINT SrcAllocationIndex;
  UINT DstAllocationIndex;
  UINT NumSubRects;
  RECT *pSubRects;
  WORD Rop;
  WORD Rop3;
  UINT SrcPitch;
  UINT DstPitch;
} DXGK_GDIARG_BITBLT;
````


## -struct-fields

### -field SrcRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that defines the rectangular area to be copied. This rectangle is specified in the coordinate system of the source surface and is defined by two points: upper left and lower right. The two points that define the rectangle are always well ordered. 

The source rectangle can exceed the bounds of the source surface.

This rectangle is mapped to the destination rectangle defined by <b>DstRect</b>. <b>SrcRect</b> is used to transform sub-rectangles from the source space to the destination space. 

For more information, see the Remarks section.


### -field DstRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that defines the rectangular area to be modified. This rectangle is specified in the coordinate system of the destination surface and is defined by two points: upper left and lower right. The rectangle is lower-right exclusive; that is, its lower and right edges are not a part of the bit-block transfer. The two points that define the rectangle are always well ordered. 

The destination rectangle defined by <b>DstRect</b> can exceed the bounds of the destination surface, but sub-rectangles cannot. Additionally, all sub-rectangles are guaranteed to fit inside the destination surface. Sub-rectangles can be constrained further by a bounding rectangle that is smaller than the destination rectangle.

For more information, see the Remarks section.


### -field SrcAllocationIndex


      [in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>SrcRect</b> source rectangle.
     


### -field DstAllocationIndex


      [in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>DstRect</b> destination rectangle.
     


### -field NumSubRects


      [in] The number of sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.
     


### -field pSubRects


      [in] A pointer to the sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.
     


### -field Rop


      [in] An 8-bit value that specifies a GDI raster operation (ROP) that is defined by the constant values of the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_gdirop_bitblt.md">DXGK_GDIROP_BITBLT</a> enumeration.
     


### -field Rop3


      [in] An 8-bit value that specifies a ternary GDI raster operation (ROP3) that combines a brush, a source bitmap, and a destination bitmap in one of 256 possible combinations. This type of raster operation will be processed only if the driver has set the <b>SupportAllBltRops</b> member in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md">DXGK_PRESENTATIONCAPS</a> structure.
     


### -field SrcPitch


      [in] The pitch of the source surface, in bytes. For more information on using pitch, see Remarks section.
     


### -field DstPitch


      [in] The pitch of the destination surface, in bytes. For more information on using pitch, see Remarks section.
     


## -remarks
The <b>SrcPitch</b> and <b>DstPitch</b> pitch values must be used to determine the byte locations of the <b>SrcRect</b> and <b>DstRect</b> rectangles, respectively, for the following allocations of type <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a>:

D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE

D3DKMDT_GDISURFACE_EXISTINGSYSMEM

Pitch should be ignored for other allocation types.

Pitch is guaranteed to be aligned in the bit-block transfer according to the <b>AlignmentShift</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md">DXGK_PRESENTATIONCAPS</a> structure (that is, <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>.PresentationCaps.AlignmentShift).

Where a rectangle is defined by two pixels at coordinates (left, top) and (right, bottom), the address of the first pixel is:

The address of the rectangle's last pixel is:

When sub-rectangles are transformed to the source surface space, the result is guaranteed to be within the source surface. This transformation is defined by the following formula:


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_gdirop_bitblt.md">DXGK_GDIROP_BITBLT</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md">DXGK_PRESENTATIONCAPS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_GDIARG_BITBLT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

