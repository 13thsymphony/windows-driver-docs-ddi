---
UID : NS:d3d12umddi.D3D12DDI_TEXTURE_LAYOUT_CAPS_0026
title : D3D12DDI_TEXTURE_LAYOUT_CAPS_0026
author : windows-driver-content
description : Specifies texture layout capabilities.
old-location : display\d3d12ddi_texture_layout_caps_0026.htm
old-project : display
ms.assetid : A64D2A22-5702-4931-AF2F-58BB919D764E
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_TEXTURE_LAYOUT_CAPS_0026, d3d12umddi/D3D12DDI_TEXTURE_LAYOUT_CAPS_0026, D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 structure [Display Devices], display.d3d12ddi_texture_layout_caps_0026
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d12umddi.h
req.include-header : D3d12umddi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3D12DDI_TEXTURE_LAYOUT_CAPS_0026
---

# D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 structure
Specifies texture layout capabilities.

## Syntax
````
typedef struct D3D12DDI_TEXTURE_LAYOUT_CAPS_0026 {
  UINT DeviceDependentLayoutCount;
  UINT DeviceDependentSwizzleCount;
  BOOL Supports64KStandardSwizzle;
  BOOL SupportsRowMajorTexture;
  BOOL IndexableSwizzlePatterns;
} D3D12DDI_TEXTURE_LAYOUT_CAPS_0026;
````

## Members


`DeviceDependentLayoutCount`

A device dependent layout count. This must be the number of device-dependent layouts supported by the adapter.

`DeviceDependentSwizzleCount`

A device dependent swizzle count. This must be the number of device-dependent swizzle patterns supported by the adapter.

`IndexableSwizzlePatterns`

Whether the texture layout can choose any swizzle pattern for a subresource.

`Supports64KStandardSwizzle`

Whether the texture layout supports 64K standard swizzle.

`SupportsRowMajorTexture`

Whether the texture layout supports row major texture.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |