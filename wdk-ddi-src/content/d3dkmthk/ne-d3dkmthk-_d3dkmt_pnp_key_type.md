---
UID: NE:d3dkmthk._D3DKMT_PNP_KEY_TYPE
title: _D3DKMT_PNP_KEY_TYPE
author: windows-driver-content
description: An enum that indicates the type of PNP key.
old-location: display\d3dkmt_pnp_key_type.htm
old-project: display
ms.assetid: 48B173D5-56C3-4611-BC55-CB7A25D05352
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_PNP_KEY_TYPE, D3DKMT_PNP_KEY_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_PNP_KEY_TYPE
req.alt-loc: d3dkmthk.h
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
req.typenames: D3DKMT_PNP_KEY_TYPE
---

# _D3DKMT_PNP_KEY_TYPE enumeration



## -description
An enum that indicates the type of PNP key. 



## -syntax

````
typedef enum _D3DKMT_PNP_KEY_TYPE { 
  D3DKMT_PNP_KEY_HARDWARE  = 1,
  D3DKMT_PNP_KEY_SOFTWARE  = 2
} D3DKMT_PNP_KEY_TYPE;
````


## -enum-fields

### -field D3DKMT_PNP_KEY_HARDWARE

Indicates that the key is a hardware key..


### -field D3DKMT_PNP_KEY_SOFTWARE

Indicates that the key is a software key.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h</dt>
</dl>
</td>
</tr>
</table>