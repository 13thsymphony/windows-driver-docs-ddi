---
UID: NS.D3DHAL._D3DHAL_DP2SETPRIORITY
title: _D3DHAL_DP2SETPRIORITY
author: windows-driver-content
description: The D3DHAL_DP2SETPRIORITY structure is used to inform the driver of the priority of the texture specified by the handle dwDDDestSurface.
old-location: display\d3dhal_dp2setpriority.htm
old-project: display
ms.assetid: 5101c150-b294-4bf4-b33c-f0fe0f54d727
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DHAL_DP2SETPRIORITY, D3DHAL_DP2SETPRIORITY
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
req.alt-api: D3DHAL_DP2SETPRIORITY
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

# _D3DHAL_DP2SETPRIORITY structure



## -description
The D3DHAL_DP2SETPRIORITY structure is used to inform the driver of the priority of the texture specified by the handle <b>dwDDDestSurface</b>.



## -syntax

````
typedef struct _D3DHAL_DP2SETPRIORITY {
  DWORD dwDDSurface;
  DWORD dwPriority;
} D3DHAL_DP2SETPRIORITY, *LPD3DHAL_DP2SETPRIORITY;
````


## -struct-fields

### -field dwDDSurface

Specifies the handle of the texture. 


### -field dwPriority

Specifies the priority of the <b>dwDDDestSurface</b> texture. A texture's priority value can be set anywhere in the range from 0 to 0xFFFFFFFF.


## -remarks
Drivers are notified of handles at texture creation time. The driver can expect to receive priority notifications only for driver-managed textures.

Priorities determine when managed textures are to be evicted from memory. A texture assigned a low priority is evicted before a texture with a high priority. If two textures have the same priority, the texture that was used more recently is kept in memory; the other texture is evicted. 


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