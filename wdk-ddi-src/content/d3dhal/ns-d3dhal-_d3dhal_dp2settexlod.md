---
UID: NS.D3DHAL._D3DHAL_DP2SETTEXLOD
title: _D3DHAL_DP2SETTEXLOD
author: windows-driver-content
description: The D3DHAL_DP2SETTEXLOD structure is used to set the level of detail (LOD) for MIP maps when the D3DDP2OP_SETTEXLOD command is sent to D3dDrawPrimitives2.
old-location: display\d3dhal_dp2settexlod.htm
old-project: display
ms.assetid: 89fc8319-64ec-4e9d-8863-e5140e9f7a44
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DHAL_DP2SETTEXLOD, D3DHAL_DP2SETTEXLOD
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
req.alt-api: D3DHAL_DP2SETTEXLOD
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

# _D3DHAL_DP2SETTEXLOD structure



## -description
The D3DHAL_DP2SETTEXLOD structure is used to set the level of detail (LOD) for MIP maps when the D3DDP2OP_SETTEXLOD command is sent to <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -syntax

````
typedef struct _D3DHAL_DP2SETTEXLOD {
  DWORD dwDDSurface;
  DWORD dwLOD;
} D3DHAL_DP2SETTEXLOD;
````


## -struct-fields

### -field dwDDSurface

Specifies a handle to a surface chain.

### -field dwLOD

Controls the maximum MIP level loaded into video memory. Therefore, if the most detailed MIP map in the chain has dimensions 256x256, setting the maximum level to 2 means that the largest MIP map ever present in video memory has dimensions 64x64. 

## -remarks

     Used only for driver-managed textures. This structure contains a surface handle to the MIP map and the maximum level of detail to set.

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
<dt>D3DDP2OP_SETTEXLOD</dt>
<dt>
<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2SETTEXLOD structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
