---
UID: NS:d3d12umddi.D3D12DDI_EXTENDED_FEATURES_FUNCS_0021
title: D3D12DDI_EXTENDED_FEATURES_FUNCS_0021
author: windows-driver-content
description: Specifies callback functions for extended features.
old-location: display\d3d12ddi_extended_features_funcs_0021.htm
old-project: display
ms.assetid: 9E2D8EF5-18D0-4BC5-ADCA-3D3BE76D3BF1
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.d3d12ddi_extended_features_funcs_0021, D3D12DDI_EXTENDED_FEATURES_FUNCS_0021, D3D12DDI_EXTENDED_FEATURES_FUNCS_0021 structure [Display Devices], d3d12umddi/D3D12DDI_EXTENDED_FEATURES_FUNCS_0021
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_EXTENDED_FEATURES_FUNCS_0021
product: Windows
targetos: Windows
req.typenames: D3D12DDI_EXTENDED_FEATURES_FUNCS_0021
---

# D3D12DDI_EXTENDED_FEATURES_FUNCS_0021 structure
Specifies callback functions for extended features.

## Syntax
````
typedef struct D3D12DDI_EXTENDED_FEATURES_FUNCS_0021 {
  PFND3D12DDI_GET_SUPPORTED_EXTENDED_FEATURES_0020         pfnGetSupportedExtendedFeatures;
  PFND3D12DDI_GET_SUPPORTED_EXTENDED_FEATURE_VERSIONS_0020 pfnGetSupportedExtendedFeatureVersions;
  PFND3D12DDI_ENABLE_EXTENDED_FEATURE_0020                 pfnEnableExtendedFeature;
  PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021          pfnSetExtendedFeatureCallbacks;
} D3D12DDI_EXTENDED_FEATURES_FUNCS_0021;
````

## Members


`pfnEnableExtendedFeature`

A callback function that enables an extended feature.

`pfnGetSupportedExtendedFeatures`

A callback function that gets supported extended features.

`pfnGetSupportedExtendedFeatureVersions`

A callback function that gets supported versions of extended features.

`pfnSetExtendedFeatureCallbacks`

A callback function that sets extended feature callbacks function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |