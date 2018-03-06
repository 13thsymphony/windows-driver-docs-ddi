---
UID: NF:prcomoem.IPrintOemDriverUni.DrvUniTextOut
title: IPrintOemDriverUni::DrvUniTextOut method
author: windows-driver-content
description: The IPrintOemDriverUni::DrvUniTextOut method is provided by the Unidrv driver so that a rendering plug-in using a device-managed drawing surface can easily output text strings.
old-location: print\iprintoemdriveruni_drvunitextout.htm
old-project: print
ms.assetid: f8c21813-9bfd-46a5-abb2-78ac2f2301af
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrvUniTextOut method [Print Devices], DrvUniTextOut method [Print Devices], IPrintOemDriverUni interface, DrvUniTextOut,IPrintOemDriverUni.DrvUniTextOut, IPrintOemDriverUni, IPrintOemDriverUni interface [Print Devices], DrvUniTextOut method, IPrintOemDriverUni::DrvUniTextOut, prcomoem/IPrintOemDriverUni::DrvUniTextOut, print.iprintoemdriveruni_drvunitextout, print_unidrv-pscript_rendering_a67dafd9-26b4-43ad-82f9-e53caca33053.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemDriverUni.DrvUniTextOut
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# DrvUniTextOut method
The <code>IPrintOemDriverUni::DrvUniTextOut</code> method is provided by the Unidrv driver so that a rendering plug-in using a device-managed drawing surface can easily output text strings.

## Syntax

````
HRESULT DrvUniTextOut(
   SURFOBJ  *pso,
   STROBJ   *pstro,
   FONTOBJ  *pfo,
   CLIPOBJ  *pco,
   RECTL    *prclExtra,
   RECTL    *prclOpaque,
   BRUSHOBJ *pboFore,
   BRUSHOBJ *pboOpaque,
   POINTL   *pptlBrushOrg,
   MIX      mix
);
````

## Parameters

`pso`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569901">SURFOBJ</a> structure that describes the surface on which to write.

`pstro`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569738">STROBJ</a> structure that defines the glyphs to be rendered and the positions in which to place them.

`pfo`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565974">FONTOBJ</a> structure from which to retrieve information about the font and its glyphs.

`pco`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539417">CLIPOBJ</a> structure that defines the clip region through which all rendering must be done. The driver cannot affect any pixels outside the clip region.

`prclExtra`

Pointer to a RECTL structure. GDI always sets this parameter to <b>NULL</b> in calls to this function. It should be ignored by the driver.

`prclOpaque`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a> structure that represents a single opaque rectangle. This rectangle is bottom-right exclusive. Pixels within this rectangle (those that are not foreground and not clipped) are to be rendered with the opaque brush. This rectangle always bounds the text to be drawn. If this parameter is <b>NULL</b>, no opaque pixels are to be rendered.

`pboFore`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538261">BRUSHOBJ</a> structure that represents the brush object to be used for the foreground pixels. This brush will always be a solid color brush.

`pboOpaque`

Pointer to a BRUSHOBJ structure that represents the opaque pixels. Both the foreground and background mix modes for this brush are assumed to be R2_COPYPEN. Unless the driver sets the GCAPS_ARBRUSHOPAQUE capabilities bit in the <b>flGraphicsCaps</b> member of the DEVINFO structure, it will always be called with a solid color brush.

`pptlBrushOrg`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569166">POINTL</a> structure that defines the brush origin for both brushes.

`mix`

The foreground and background raster operations (mix modes) for <i>pboFore</i>.


## Return Value

The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>

## Remarks

The <code>IPrintOemDriverUni::DrvUniTextOut</code> method is provided by Unidrv for use by rendering plug-ins that support a device-managed drawing surface. Such rendering plug-ins must hook out Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557277">DrvTextOut</a> function, and the <code>IPrintOemDriverUni::DrvUniTextOut</code> method is meant to be called from that hooking function. The hooking function must perform text region clipping and text rotation operations. It can then call <code>IPrintOemDriverUni::DrvUniTextOut</code> to request Unidrv to create the text string using downloadable fonts (and to perform glyph-based clipping).

If <code>IPrintOemDriverUni::DrvUniTextOut</code> cannot create the text string, either because the font is not available or is rotated, it calls the rendering plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554277">IPrintOemUni::TextOutAsBitmap</a> method, which draws the text string as a bitmap.

For more information, see <a href="https://msdn.microsoft.com/4403165f-c528-450e-9c96-77a9ce0778aa">Handling Device-Managed Surfaces</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |
| **Library** | prcomoem.h |