---
UID: NS.d3dhal._D3DHAL_DP2VIEWPORTINFO
title: D3DHAL_DP2VIEWPORTINFO
author: windows-driver-content
description: The D3DHAL_DP2VIEWPORTINFO structure is used to inform guard-band aware drivers of the view clipping rectangle. The clipping rectangle is specified by the members dwX, dwY, dwWidth and dwHeight.
old-location: display\d3dhal_dp2viewportinfo.htm
old-project: display
ms.assetid: df46a37e-fed6-4738-8794-6611e9c758cb
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DHAL_DP2VIEWPORTINFO, D3DHAL_DP2VIEWPORTINFO
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
req.alt-api: D3DHAL_DP2VIEWPORTINFO
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

# D3DHAL_DP2VIEWPORTINFO structure



## -description
<p>The D3DHAL_DP2VIEWPORTINFO structure is used to inform guard-band aware drivers of the view clipping rectangle. The clipping rectangle is specified by the members <b>dwX</b>, <b>dwY</b>, <b>dwWidth</b> and <b>dwHeight</b>.</p>


## -syntax

````
typedef struct _D3DHAL_DP2VIEWPORTINFO {
  DWORD dwX;
  DWORD dwY;
  DWORD dwWidth;
  DWORD dwHeight;
} D3DHAL_DP2VIEWPORTINFO, *LPD3DHAL_DP2VIEWPORTINFO;
````


## -struct-fields
<dl>

### -field dwX

<dd></dd>

### -field dwY

<dd>
<p>Specify the location, in screen coordinates, of the upper-left corner of the subrectangle.</p>
</dd>

### -field dwWidth

<dd></dd>

### -field dwHeight

<dd>
<p>Specify the width and height, respectively, of the subrectangle where the application is rendering. These members are specified in screen coordinates.</p>
</dd>
</dl>

## -remarks
<p>The <a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a> callback parses a D3DHAL_DP2VIEWPORTINFO structure from the command buffer and updates the driver's viewport description when <a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a> is set to D3DDP2OP_VIEWPORTINFO.</p>

<p>One D3DHAL_DP2VIEWPORTINFO structure follows the D3DHAL_DP2COMMAND structure in the command buffer.</p>

<p>The driver should update the viewport portion of its internal rendering context with the location and size values specified in this structure. The driver can use this information to perform guard band clipping.</p>

<p>Subguard-band drivers should ignore and skip over these instructions and continue processing the rest of the command buffer.</p>

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
<dt>D3DDP2OP_VIEWPORTINFO</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal-drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
<dt>
<a href="..\d3dhal\ns-d3dhal--d3dhal-dp2command.md">D3DHAL_DP2COMMAND</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2VIEWPORTINFO structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
