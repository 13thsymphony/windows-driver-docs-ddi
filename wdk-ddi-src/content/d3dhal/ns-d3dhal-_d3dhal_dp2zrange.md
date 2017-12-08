---
UID: NS.D3DHAL._D3DHAL_DP2ZRANGE
title: _D3DHAL_DP2ZRANGE
author: windows-driver-content
description: The D3DHAL_DP2ZRANGE structure specifies z-range minimum and maximum in D3dDrawPrimitives2.
old-location: display\d3dhal_dp2zrange.htm
old-project: display
ms.assetid: 329e0036-2d67-465f-a049-a36648622003
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DHAL_DP2ZRANGE, D3DHAL_DP2ZRANGE
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
req.alt-api: D3DHAL_DP2ZRANGE
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
---

# _D3DHAL_DP2ZRANGE structure



## -description
The D3DHAL_DP2ZRANGE structure specifies z-range minimum and maximum in <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -syntax

````
typedef struct _D3DHAL_DP2ZRANGE {
  D3DVALUE dvMinZ;
  D3DVALUE dvMaxZ;
} D3DHAL_DP2ZRANGE, *LPD3DHAL_DP2ZRANGE;
````


## -struct-fields

### -field dvMinZ

Specifies the minimum z value for the Mvs matrix described in the <a href="https://msdn.microsoft.com/b45aa56e-2d8c-412a-b581-a1e2002d4fac">Hardware Transform and Lighting</a> section of the design guide.

### -field dvMaxZ

Specifies the maximum z value for the Mvs matrix described in the <a href="https://msdn.microsoft.com/b45aa56e-2d8c-412a-b581-a1e2002d4fac">Hardware Transform and Lighting</a> section of the design guide.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
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
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2ZRANGE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
