---
UID: NS.D3DUMDDI._DXVAHDDDI_SURFACE
title: _DXVAHDDDI_SURFACE
author: windows-driver-content
description: The DXVAHDDDI_SURFACE structure describes a surface.
old-location: display\dxvahdddi_surface.htm
old-project: display
ms.assetid: a0bfc9bf-777e-4da4-9414-856ec650375d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXVAHDDDI_SURFACE, DXVAHDDDI_SURFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_SURFACE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_SURFACE
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
---

# _DXVAHDDDI_SURFACE structure



## -description
The DXVAHDDDI_SURFACE structure describes a surface. 


## -syntax

````
typedef struct _DXVAHDDDI_SURFACE {
  HANDLE hResource;
  UINT   SubResourceIndex;
} DXVAHDDDI_SURFACE;
````


## -struct-fields

### -field hResource

[in] A handle to the resource that contains the surface. 

### -field SubResourceIndex

[in] The zero-based index into the resource, which the handle in the <b>hResource</b> member specifies. The <b>SubResourceIndex</b> index indicates the surface. 

## -remarks
DXVAHDDDI_SURFACE structures are used to describe surfaces in members of the <a href="display.dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a> and <a href="display.d3dddiarg_dxvahd_videoprocessblthd">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a> structures in a call to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_videoprocessblthd.md">VideoProcessBltHD</a> function.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
DXVAHDDDI_SURFACE is supported beginning with the Windows 7 operating system.
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

## -see-also
<dl>
<dt>
<a href="display.d3dddiarg_dxvahd_videoprocessblthd">D3DDDIARG_DXVAHD_VIDEOPROCESSBLTHD</a>
</dt>
<dt>
<a href="display.dxvahdddi_stream_data">DXVAHDDDI_STREAM_DATA</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_dxvahd_videoprocessblthd.md">VideoProcessBltHD</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_SURFACE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
