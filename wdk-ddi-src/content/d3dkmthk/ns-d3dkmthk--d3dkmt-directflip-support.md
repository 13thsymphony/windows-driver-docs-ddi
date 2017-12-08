---
UID: NS.d3dkmthk._D3DKMT_DIRECTFLIP_SUPPORT
title: D3DKMT_DIRECTFLIP_SUPPORT
author: windows-driver-content
description: Indicates whether the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the Desktop Window Manager (DWM) managed primary allocations.
old-location: display\d3dkmt_directflip_support.htm
old-project: display
ms.assetid: d579d9a3-7db1-47ed-859d-3fed99a4ee9d
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_DIRECTFLIP_SUPPORT, D3DKMT_DIRECTFLIP_SUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_DIRECTFLIP_SUPPORT
req.alt-loc: D3dkmthk.h
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

# D3DKMT_DIRECTFLIP_SUPPORT structure



## -description
<p>Indicates whether the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the Desktop Window Manager (DWM) managed primary allocations.</p>


## -syntax

````
typedef struct _D3DKMT_DIRECTFLIP_SUPPORT {
  BOOL Supported;
} D3DKMT_DIRECTFLIP_SUPPORT;
````


## -struct-fields
<dl>

### -field Supported

<dd>
<p>If <b>TRUE</b>, the driver supports Direct Flip operations. Otherwise, the driver does not support Direct Flip operations.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>