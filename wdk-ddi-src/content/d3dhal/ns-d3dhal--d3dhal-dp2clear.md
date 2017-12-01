---
UID: NS.d3dhal._D3DHAL_DP2CLEAR
title: D3DHAL_DP2CLEAR
author: windows-driver-content
description: D3DHAL_DP2CLEAR contains all of the information that the driver needs to perform hardware-assisted clearing on the rendering target, depth buffer or stencil buffer.
old-location: display\d3dhal_dp2clear.htm
old-project: display
ms.assetid: 8cd81cae-8d6b-48d8-afdc-87e3a81653f4
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2CLEAR, D3DHAL_DP2CLEAR
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
req.alt-api: D3DHAL_DP2CLEAR
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

# D3DHAL_DP2CLEAR structure



## -description
<p>D3DHAL_DP2CLEAR contains all of the information that the driver needs to perform hardware-assisted clearing on the rendering target, depth buffer or stencil buffer.</p>


## -syntax

````
typedef struct _D3DHAL_DP2CLEAR {
  DWORD    dwFlags;
  DWORD    dwFillColor;
  D3DVALUE dvFillDepth;
  DWORD    dwFillStencil;
  RECT     Rects[1];
} D3DHAL_DP2CLEAR, *LPD3DHAL_DP2CLEAR;
````


## -struct-fields
<dl>

### -field <b>dwFlags</b>

<dd>
<p>Specifies what buffers the driver should clear. This member can be a bitwise OR of the following values:</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>D3DCLEAR_TARGET</p>
</td>
<td>
<p>The driver should clear the context's render target to the color specified by the <b>dwFillColor</b> member.</p>
</td>
</tr>
<tr>
<td>
<p>D3DCLEAR_STENCIL</p>
</td>
<td>
<p>The driver should clear the context's stencil buffer to the value specified by the <b>dwFillStencil</b> member.</p>
</td>
</tr>
<tr>
<td>
<p>D3DCLEAR_ZBUFFER</p>
</td>
<td>
<p>The driver should clear the context's depth buffer to the depth specified by the <b>dwFillDepth</b> member.</p>
</td>
</tr>
<tr>
<td>
<p>D3DCLEAR_COMPUTERECTS</p>
</td>
<td>
<p>DirectX 8.0 and later versions only.</p>
<p>If this flag is set, the specified rectangles should be clipped against the current viewport. Furthermore, it is possible that when D3DCLEAR_COMPUTERECTS is specified the number of rectangles to clear can be zero (the number of rectangles to clear can be found in the <b>wStateCount</b>/<b>wPrimtiveCount</b> union of the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> structure for the clear). In this case the entire viewport should be cleared.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field <b>dwFillColor</b>

<dd>
<p>Specifies the color that the driver should clear the context's render target to.</p>
</dd>

### -field <b>dvFillDepth</b>

<dd>
<p>Specifies the value that the driver should use to set the depth in the context's depth buffer. This member can be a value in the interval 0.0 to 1.0. The driver should convert this value to an integer using the <b>dwZBitMask</b> member of the depth buffer's <a href="..\ksmedia\ns-ksmedia--ddpixelformat.md">DDPIXELFORMAT</a> structure.</p>
</dd>

### -field <b>dwFillStencil</b>

<dd>
<p>Specifies the value that the driver should clear the context's stencil buffer to. This member can be an integer in the interval 0 to 2ⁿ-1, where <i>n</i> is the number of bits in the stencil buffer.</p>
</dd>

### -field <b>Rects</b>

<dd>
<p>Specifies the rectangular areas of the buffer that the driver should clear. The rectangles are specified in screen coordinates. This member of the structure contains the first rectangle area to be blitted. The <b>wStateCount</b> member of the <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> contains the total number of rectangle areas to be blitted. The other (<b>wStateCount</b>-1) RECT structures required follow the D3DHAL_DP2CLEAR structure without any padding.</p>
</dd>
</dl>

## -remarks
<p>This structure is used with the D3DDP2OP_CLEAR command token to replace the legacy <b>D3dClear</b> and <b>D3dClear2</b> callbacks.</p>

<p>It is important to note that when the number of rectangles is zero, the D3DHAL_DP2CLEAR data structure still includes space for a single RECT. Thus, the size of this single RECT should be included when advancing to the next DP2 instruction. However, the contents of the RECT in this case are undefined and the driver should not attempt to read them.</p>

<p>Display drivers must convert input color values for the ARGB and YUV classes of color formats. For clear operations, input color values are specified in the <b>dwFillColor</b> member. For more information, see <a href="https://msdn.microsoft.com/53ce6be1-14e1-4ee8-ba29-f198dcdacdaa">Handling Color Values for Pixel Formats</a>.</p>

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

## -see-also
<dl>
<dt>D3DDP2OP_CLEAR</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
<dt>
<a href="..\ksmedia\ns-ksmedia--ddpixelformat.md">DDPIXELFORMAT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2CLEAR structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
