---
UID: NC:d3d10umddi.PFND3D11_1DDI_CLEARVIEW
title: PFND3D11_1DDI_CLEARVIEW
author: windows-driver-content
description: Sets all the elements in a resource view to one value. A resource view is a surface descriptor that indicates a format and possibly a subset of the resource.
old-location: display\clearview.htm
old-project: display
ms.assetid: c3cc08ea-22db-4fae-a180-76f3babd1c5c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _POWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ClearView
req.alt-loc: D3d10umddi.h
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
req.typenames: POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX
---

# PFND3D11_1DDI_CLEARVIEW callback



## -description
Sets all the elements in a resource view to one value. A resource view is  a surface descriptor  that indicates a format and possibly a subset of the resource.



## -prototype

````
PFND3D11_1DDI_CLEARVIEW ClearView;

VOID APIENTRY* ClearView(
             D3D10DDI_HDEVICE    hDevice,
             D3D11DDI_HANDLETYPE HandleType,
             VOID                *hView,
       const FLOAT               Color[4],
  _In_ const D3D10_DDI_RECT      *pRect,
             UINT                NumRects
)
{ ... }
````


## -parameters

### -param hDevice 

A handle to the display device (graphics context).


### -param HandleType 

A value, of type <a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_handletype.md">D3D11DDI_HANDLETYPE</a>, that identifies the view handle type that supports this clear operation. Possible types are the following.

<ul>
<li><b>D3D10DDI_HT_RENDERTARGETVIEW</b></li>
<li><b>D3D11DDI_HT_UNORDEREDACCESSVIEW</b></li>
<li>Any <b>D3D11_1DDI_HT_VIDEOXXX</b> type</li>
</ul>

### -param hView 

A pointer to the resource view to clear.


### -param Color 

A 4-component array that represents the color to use to clear the resource view. For more details, see the Remarks section.


### -param pRect [in]

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structures for the rectangles in the resource view to clear. If <b>NULL</b>, <i>ClearView</i> clears the entire surface.


### -param NumRects 

The number of rectangles in the array that the  <i>pRect</i> parameter specifies.


## -returns
This callback function does not return a value.


## -remarks
<i>ClearView</i> works only on render-target views (RTVs), unordered-access views (UAVs), or any video view of a <a href="https://msdn.microsoft.com/e9cd2bc7-99c1-4aca-91b0-9faefa4a856d">Texture2D</a> surface. Empty rectangles in the <i>pRect</i> array are a no-op. A rectangle is empty if the top value equals the bottom value or the left value equals the right value.

<i>ClearView</i> does not support 3-D textures.

<i>ClearView</i> applies the same color value to all array slices in a view; all rectangles in the <i>pRect</i> array correspond to each array slice.  The <i>pRect</i> array of rectangles is a set of areas to clear on a single surface.  If the view is an array, <i>ClearView</i> clears all the rectangles on each array slice individually.

When the user-mode driver applies rectangles to buffers, it should set the top value to 0 and the bottom value to 1 and set the left value and right value to describe the extent within the buffer. When the top value equals the bottom value or the left value equals the right value, the rectangle is empty and a no-op is achieved.

The driver should convert and clamp color values to the destination format as appropriate per Direct3D conversion rules.  For example, if the format of the view is <a href="direct3ddxgi.dxgi_format#DXGI_FORMAT_R8G8B8A8_UNORM#DXGI_FORMAT_R8G8B8A8_UNORM"><b>DXGI_FORMAT_R8G8B8A8_UNORM</b></a>, clamp inputs to 0.0f to 1.0f (+INF -&gt; 1.0f (0XFF)/NaN -&gt; 0.0f).

If the format is integer, such as <a href="direct3ddxgi.dxgi_format#DXGI_FORMAT_R8G8B8A8_UINT#DXGI_FORMAT_R8G8B8A8_UINT"><b>DXGI_FORMAT_R8G8B8A8_UINT</b></a>, take inputs as integral floats. Therefore, 235.0f maps to 235 (rounds to zero, out of range/INF values clamp to target range, and NaN to zero).

Here are the color mappings:

For video views with YUV or YCbBr formats, <i>ClearView</i> does not convert color values. In situations where the format name does not indicate _UNORM,  _UINT, and so on, <i>ClearView</i> assumes _UINT. Therefore, 235.0f maps to 235 (rounds to zero, out of range/INF values clamp to target range, and NaN to zero).

For Microsoft Direct3D views of the subsampled RTV or UAV video surfaces, note that the dimensions of the view are based on how many pixels are in the view format rather than the underlying logical number of video pixels.  For example suppose the surface has format YUY2 with dimension 1920 by 1080 pixels and an RTV uses the format <a href="direct3ddxgi.dxgi_format#DXGI_FORMAT_R8G8B8A8_UINT#DXGI_FORMAT_R8G8B8A8_UINT"><b>DXGI_FORMAT_R8G8B8A8_UINT</b></a>.  The view appears to Direct3D as having 1920/2 = 960 <b>R8G8B8A8</b> pixels in the horizontal direction.  So any rectangles passed into <i>ClearView</i> are interpreted in this space.  Furthermore, the clear value is taken for all 4 components, <b>R8G8B8A8</b>, as if it is no different from a true <b>R8G8B8A8</b> surface.  In this case, R, G, B, and A do not mean standard RGBA color values; instead, they identify a location in memory, and the caller is responsible for understanding what it means to put data into that location in the context of a video surface.

However, video views of a video surface (such as views provided to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview.md">CreateVideoDecoderOutputView</a> function and other <b>XxxInputView</b> and <b>XxxOutputView</b> functions) appear at the full logical dimensions. In this case, the horizontal dimension is 1920 pixels wide, so <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structures passed into <i>ClearView</i> honor that. Such  <b>RECT</b>s  must be aligned so they do not straddle subsampled blocks, otherwise the runtime will drop the call to this function. For video views, YUV colors must be appropriately replicated for subsampled formats. For example, YUV in the <i>ClearView</i> call has the Y value duplicated for each block in a YUY2 surface.


    The <b>D3D10_DDI_RECT</b> structure is defined as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure.


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoderoutputview.md">CreateVideoDecoderOutputView</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi_handletype.md">D3D11DDI_HANDLETYPE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CLEARVIEW callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

