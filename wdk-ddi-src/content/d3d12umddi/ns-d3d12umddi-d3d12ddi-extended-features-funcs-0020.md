---
UID: NS.d3d12umddi.D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
title: D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
author: windows-driver-content
description: This structure contains device functions for extended features in video.
old-location: display\d3d12ddi_extended_features_funcs_0020.htm
old-project: display
ms.assetid: 36AAD6F2-3220-4F9A-AA10-BA8D87948D09
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D12DDI_EXTENDED_FEATURES_FUNCS_0020, D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
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
req.alt-api: D3D12DDI_EXTENDED_FEATURES_FUNCS_0020
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

# D3D12DDI_EXTENDED_FEATURES_FUNCS_0020 structure



## -description
<p>This structure contains device functions for extended features in  video.</p>


## -syntax

````
typedef struct _D3D12DDI_EXTENDED_FEATURES_FUNCS_0020 {
  PFND3D12DDI_GET_SUPPORTED_EXTENDED_FEATURES_0020         pfnGetSupportedExtendedFeatures;
  PFND3D12DDI_GET_SUPPORTED_EXTENDED_FEATURE_VERSIONS_0020 pfnGetSupportedExtendedFeatureVersions;
  PFND3D12DDI_ENABLE_EXTENDED_FEATURE                      pfnEnableExtendedFeature;
} D3D12DDI_EXTENDED_FEATURES_FUNCS_0020;
````


## -struct-fields
<dl>

### -field pfnGetSupportedExtendedFeatures

<dd>
<p>A pointer for a callback function to get supported extended features.</p>
</dd>

### -field pfnGetSupportedExtendedFeatureVersions

<dd>
<p>A pointer for a callback function to get the supported versions of extended features.</p>
</dd>

### -field pfnEnableExtendedFeature

<dd>
<p>A pointer for a callback function to enable an extended feature.</p>
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