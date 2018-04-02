---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_COPYTILEMAPPINGS
title: PFND3DWDDM1_3DDI_COPYTILEMAPPINGS
author: windows-driver-content
description: Copies mappings from a source tiled resource to a destination tiled resource.
old-location: display\copytilemappings.htm
old-project: display
ms.assetid: CB2CE5E7-DDD4-4782-BB91-67A2C562A975
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CopyTileMappings, CopyTileMappings callback function [Display Devices], PFND3DWDDM1_3DDI_COPYTILEMAPPINGS, d3d10umddi/CopyTileMappings, display.copytilemappings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	CopyTileMappings
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3DWDDM1_3DDI_COPYTILEMAPPINGS callback function
Copies mappings from a source tiled resource to a destination tiled resource.

## Syntax

```
PFND3DWDDM1_3DDI_COPYTILEMAPPINGS Pfnd3dwddm13DdiCopytilemappings;

void Pfnd3dwddm13DdiCopytilemappings(
  D3D10DDI_HDEVICE hDevice,
  D3D10DDI_HRESOURCE hDestTiledResource,
  const D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE *pDestRegionStartCoord,
  D3D10DDI_HRESOURCE hSourceTiledResource,
  const D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE *pSourceRegionStartCoord,
  const D3DWDDM1_3DDI_TILE_REGION_SIZE *pTileRegionSize,
  UINT Flags
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`hDestTiledResource`

A handle to the destination tiled resource.

`*pDestRegionStartCoord`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn440996">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the destination tiled resource.

`hSourceTiledResource`

A handle to the source tiled resource.

`*pSourceRegionStartCoord`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn440996">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the source tiled resource.

`*pTileRegionSize`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn440997">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structure that describes the size of the tiled region.

`Flags`

A combination of <a href="https://msdn.microsoft.com/library/windows/hardware/dn458990">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.


## Return Value

None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. The driver can set <b>E_INVALIDARG</b> if an input parameter does not exist or is <b>NULL</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1,WDDM 1.3 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn440996">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn458990">D3DWDDM1_3DDI_TILE_MAPPING_FLAG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn440997">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>