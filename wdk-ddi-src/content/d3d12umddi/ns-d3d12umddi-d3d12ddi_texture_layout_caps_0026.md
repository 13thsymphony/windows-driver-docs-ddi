---
UID: NS.D3D12UMDDI.D3D12DDI_TEXTURE_LAYOUT_CAPS_0026
title: D3D12DDI_TEXTURE_LAYOUT_CAPS_0026
author: windows-driver-content
description: Specifies texture layout capabilities.
old-location: display\d3d12ddi_texture_layout_caps_0026.htm
old-project: display
ms.assetid: A64D2A22-5702-4931-AF2F-58BB919D764E
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDI_TEXTURE_LAYOUT_CAPS_0026, D3D12DDI_TEXTURE_LAYOUT_CAPS_0026
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
req.alt-api: D3D12DDI_TEXTURE_LAYOUT_CAPS_0026
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
---

# D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 structure



## -description
Specifies texture layout capabilities.



## -syntax

````
typedef struct D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 {
  UINT DeviceDependentLayoutCount;
  UINT DeviceDependentSwizzleCount;
  BOOL Supports64KStandardSwizzle;
  BOOL SupportsRowMajorTexture;
  BOOL IndexableSwizzlePatterns;
} D3D12DDI_TEXTURE_LAYOUT_CAPS_0026;
````


## -struct-fields

### -field DeviceDependentLayoutCount

A device dependent layout count. This must be the number of device-dependent layouts supported by the adapter. 


### -field DeviceDependentSwizzleCount

A device dependent swizzle count. This must be the number of device-dependent swizzle patterns supported by the adapter. 


### -field Supports64KStandardSwizzle

Whether the texture layout supports 64K standard swizzle.


### -field SupportsRowMajorTexture

Whether the texture layout supports row major texture.


### -field IndexableSwizzlePatterns

Whether the texture layout can choose any swizzle pattern for a subresource. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>