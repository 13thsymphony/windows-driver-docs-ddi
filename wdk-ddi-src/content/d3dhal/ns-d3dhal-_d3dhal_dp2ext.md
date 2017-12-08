---
UID: NS.D3DHAL._D3DHAL_DP2EXT
title: _D3DHAL_DP2EXT
author: windows-driver-content
description: The D3DHAL_DP2EXT structure's use has yet to be defined.
old-location: display\d3dhal_dp2ext.htm
old-project: display
ms.assetid: d7cec277-d1d3-4c0f-91ec-fd5e962b6e1c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DHAL_DP2EXT, D3DHAL_DP2EXT
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
req.alt-api: D3DHAL_DP2EXT
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

# _D3DHAL_DP2EXT structure



## -description
The D3DHAL_DP2EXT structure's use has yet to be defined.


## -syntax

````
typedef struct _D3DHAL_DP2EXT {
  DWORD dwExtToken;
  DWORD dwSize;
} D3DHAL_DP2EXT, *LPD3DHAL_DP2EXT;
````


## -struct-fields

### -field dwExtToken

Specifies the extension token.

### -field dwSize

Specifies the size, in bytes of this structure.  

## -remarks
This structure is used with hardware transform and lighting. Contact the DirectX team at Microsoft for further implementation details.

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