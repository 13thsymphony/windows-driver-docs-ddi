---
UID: NS.d3dumddi._DXVAHDDDI_CONTENT_DESC
title: DXVAHDDDI_CONTENT_DESC
author: windows-driver-content
description: The DXVAHDDDI_CONTENT_DESC structure describes the video content that a decode device processes.
old-location: display\dxvahdddi_content_desc.htm
old-project: display
ms.assetid: 635a4a47-11b8-4d78-871e-21ee438880df
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXVAHDDDI_CONTENT_DESC, DXVAHDDDI_CONTENT_DESC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_CONTENT_DESC is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_CONTENT_DESC
req.alt-loc: d3dumddi.h
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

# DXVAHDDDI_CONTENT_DESC structure



## -description
<p>The DXVAHDDDI_CONTENT_DESC structure describes the video content that a decode device processes. </p>


## -syntax

````
typedef struct _DXVAHDDDI_CONTENT_DESC {
  DXVAHDDDI_FRAME_FORMAT InputFrameFormat;
  DXVAHDDDI_RATIONAL     InputFrameRate;
  UINT                   InputWidth;
  UINT                   InputHeight;
  DXVAHDDDI_RATIONAL     OutputFrameRate;
  UINT                   OutputWidth;
  UINT                   OutputHeight;
} DXVAHDDDI_CONTENT_DESC;
````


## -struct-fields
<dl>

### -field InputFrameFormat

<dd>
<p>[in] A <a href="..\d3dumddi\ne-d3dumddi--dxvahdddi-frame-format.md">DXVAHDDDI_FRAME_FORMAT</a>-typed value that indicates the frame format of the input video stream. </p>
</dd>

### -field InputFrameRate

<dd>
<p>
      [in] A <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-rational.md">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents the frame rate of the input video stream. 
     </p>
</dd>

### -field InputWidth

<dd>
<p>[in] The width, in pixels, of the input video stream. </p>
</dd>

### -field InputHeight

<dd>
<p>[in] The height, in pixels, of the input video stream. </p>
</dd>

### -field OutputFrameRate

<dd>
<p>
      [in] A <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-rational.md">DXVAHDDDI_RATIONAL</a> structure that specifies a fractional value that represents the frame rate of the output. 
     </p>
</dd>

### -field OutputWidth

<dd>
<p>[in] The width, in pixels, of the output video stream. </p>
</dd>

### -field OutputHeight

<dd>
<p>[in] The height, in pixels, of the output video stream. </p>
</dd>
</dl>

## -remarks
<p>The driver can use the information in the members of DXVAHDDDI_CONTENT_DESC to optimize its capabilities. For example, the driver might not require to expose costly capabilities for high-definition content and the de-interlacing capability for progressive content. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>DXVAHDDDI_CONTENT_DESC is supported beginning with the Windows 7 operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ne-d3dumddi--dxvahdddi-frame-format.md">DXVAHDDDI_FRAME_FORMAT</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-rational.md">DXVAHDDDI_RATIONAL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_CONTENT_DESC structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
