---
UID: NS.d3d12umddi.D3D12DDI_TEXTURE_LAYOUT_CAPS_0001
title: D3D12DDI_TEXTURE_LAYOUT_CAPS_0001
author: windows-driver-content
description: Specifies texture layout capabilities.
old-location: display\d3d12ddi_texture_layout_caps_0001.htm
old-project: display
ms.assetid: CFA0C474-129A-4A05-B426-520B96C318D8
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D12DDI_TEXTURE_LAYOUT_CAPS_0001, D3D12DDI_TEXTURE_LAYOUT_CAPS_0001
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_TEXTURE_LAYOUT_CAPS_0001
req.alt-loc: D3d12umddi.h
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

# D3D12DDI_TEXTURE_LAYOUT_CAPS_0001 structure



## -description
<p>Specifies texture layout capabilities.</p>


## -syntax

````
typedef struct D3D12DDI_TEXTURE_LAYOUT_CAPS_0001 {
  UINT DeviceDependentLayoutCount;
  UINT DeviceDependentSwizzleCount;
  BOOL Supports64KStandardSwizzle;
} D3D12DDI_TEXTURE_LAYOUT_CAPS_0001;
````


## -struct-fields
<dl>

### -field DeviceDependentLayoutCount

<dd>
<p>A device dependent layout count. This must be the number of device-dependent layouts supported by the adapter. </p>
</dd>

### -field DeviceDependentSwizzleCount

<dd>
<p>A device dependent swizzle count. This must be the number of device-dependent swizzle patterns supported by the adapter. </p>
</dd>

### -field Supports64KStandardSwizzle

<dd>
<p>Whether the texture layout supports 64K standard swizzle.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>