---
UID: NS:d3dkmddi._DXGK_GDIARG_TRANSPARENTBLT
title: _DXGK_GDIARG_TRANSPARENTBLT
author: windows-driver-content
description: The DXGK_GDIARG_TRANSPARENTBLT structure describes the characteristics of a GDI hardware-accelerated bit-block transfer (bitblt) operation with transparency.
old-location: display\dxgk_gdiarg_transparentblt.htm
old-project: display
ms.assetid: 2536fafc-3b62-42a6-8b53-60fa8d61d5a9
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GDIARG_TRANSPARENTBLT, DXGK_GDIARG_TRANSPARENTBLT
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
req.alt-api: DXGK_GDIARG_TRANSPARENTBLT
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
req.typenames: DXGK_GDIARG_TRANSPARENTBLT
---

# _DXGK_GDIARG_TRANSPARENTBLT structure



## -description
The DXGK_GDIARG_TRANSPARENTBLT structure describes the characteristics of a GDI hardware-accelerated bit-block transfer (bitblt) operation with transparency.



## -syntax

````
typedef struct _DXGK_GDIARG_TRANSPARENTBLT {
  RECT                      SrcRect;
  RECT                      DstRect;
  UINT                      SrcAllocationIndex;
  UINT                      DstAllocationIndex;
  UINT                      Color;
  UINT                      NumSubRects;
  RECT                      *pSubRects;
  D3DKM_TRANSPARENTBLTFLAGS Flags;
  UINT                      SrcPitch;
} DXGK_GDIARG_TRANSPARENTBLT;
````


## -struct-fields

### -field SrcRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that defines the rectangular area to be copied. This rectangle is specified in the coordinate system of the source surface and is defined by two points: upper left and lower right. The two points that define the rectangle are always well ordered. 

For more information, see the Remarks section.


### -field DstRect

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that defines the rectangular area to be modified. This rectangle is specified in the coordinate system of the destination surface and is defined by two points: upper left and lower right. The rectangle is lower-right exclusive; that is, its lower and right edges are not a part of the bit-block transfer. The two points that define the rectangle are always well ordered. 

The destination rectangle defined by <b>DstRect</b> can exceed the bounds of the destination surface, but sub-rectangles cannot. Additionally, all sub-rectangles are guaranteed to fit inside the destination surface. Sub-rectangles can be constrained further by a bounding rectangle that is smaller than the destination rectangle. 

For more information, see the Remarks section.


### -field SrcAllocationIndex


      [in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>SrcRect</b> source rectangle.
     


### -field DstAllocationIndex


      [in] An index of the element in the allocation list that specifies the allocation that is referenced by the <b>DstRect</b> destination rectangle.
     


### -field Color


      [in] Specifies the physical transparent color in the source surface, in 32-bit ARGB unsigned pixel format (as defined by the D3DDDIFMT_A8R8G8B8 value of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a> enumeration). Any pixels on the source surface that match the transparent color that is specified by <b>Color</b> are not copied.
     


### -field NumSubRects


      [in] The number of sub-rectangles in the destination surface space that is bounded by the <b>DstRect</b> destination rectangle.
     


### -field pSubRects


      [in] A pointer to the sub-rectangles in the destination surface space.
     


### -field Flags


      [in] A <a href="..\d3dkmddi\ns-d3dkmddi-_d3dkm_transparentbltflags.md">D3DKM_TRANSPARENTBLTFLAGS</a> structure that specifies the display adapter's hardware-accelerated transparent bit-block transfer capabilities.
     


### -field SrcPitch


      [in] The pitch of the source surface, in bytes.
     


## -remarks
The rectangles that are specified by the <b>SrcRect</b> and <b>DstRect</b> members bound all sub-rectangles in the source and destination surface spaces, respectively. The Microsoft DirectX graphics kernel subsystem will never request a transparent bit-block transfer if the source and destination rectangles overlap on the same surface.

To complete the transparent bit-block transfer operation, the color of each pixel in <b>DstRect</b> should be computed by using the following formula:

In this case, a value of 0x00FFFFFF in ARGB format indicates alpha = 0, hence alpha-blending is not implemented.

If a stretch bit-block transfer operation is required, the x and y stretch ratios are computed respectively as the ratios of the x and y sizes of <b>DstRect</b> and <b>SrcRect</b>. Additionally, the stretch operation will proceed as if the COLORONCOLOR value in <i>Wingdi.h</i> is set. In a shrinking bit-block transfer, enough pixels should be ignored so that pixels do not need to be combined. In a stretching bit-block transfer, pixels should be replicated.

For more information about transparent bit-block transfers, see <a href="https://msdn.microsoft.com/76e07c66-7e57-42d7-b6da-c13c8e9a8dee">Copying Bitmaps</a>.

When sub-rectangles are transformed to the source surface space, the result is guaranteed to be within the source surface. The transformation of a sub-rectangle's coordinates in the destination surface to coordinates  in the source surface is defined by the following formulas, where


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_d3dkm_transparentbltflags.md">D3DKM_TRANSPARENTBLTFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_renderkm_command.md">DXGK_RENDERKM_COMMAND</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_GDIARG_TRANSPARENTBLT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

