---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_COPYTILES
title: PFND3DWDDM1_3DDI_COPYTILES
author: windows-driver-content
description: Copies tiles from buffer to tiled resource or vice versa.
old-location: display\copytiles.htm
old-project: display
ms.assetid: 8DA0FF6C-CA2C-4943-93C3-BFC3773617CC
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: CopyTiles, CopyTiles callback function [Display Devices], PFND3DWDDM1_3DDI_COPYTILES, d3d10umddi/CopyTiles, display.copytiles
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
-	CopyTiles
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3DWDDM1_3DDI_COPYTILES callback function
Copies tiles from buffer to tiled resource or vice versa.

## Syntax

```
PFND3DWDDM1_3DDI_COPYTILES Pfnd3dwddm13DdiCopytiles;

void Pfnd3dwddm13DdiCopytiles(
  D3D10DDI_HDEVICE hDevice,
  D3D10DDI_HRESOURCE hTiledResource,
  const D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE *pTileRegionStartCoord,
  const D3DWDDM1_3DDI_TILE_REGION_SIZE *pTileRegionSize,
  D3D10DDI_HRESOURCE hBuffer,
  UINT64 BufferStartOffsetInBytes,
  UINT Flags
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`hTiledResource`

A handle to the tiled resource.

`*pTileRegionStartCoord`

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a> structure that describes the starting coordinates of the destination tiled resource.

`*pTileRegionSize`

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size.md">D3DWDDM1_3DDI_TILE_REGION_SIZE</a> structure that describes the size of the tiled region.

`hBuffer`

A handle to a resource that represents a default, dynamic, or staging buffer.

`BufferStartOffsetInBytes`

The offset, in bytes, into the buffer at <i>hBuffer</i> to start the operation.

`Flags`

A combination of <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tile_copy_flag.md">D3DWDDM1_3DDI_TILE_COPY_FLAG</a> values that are combined by using a bitwise <b>OR</b> operation.


## Return Value

None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code.

The Direct3D runtime does not expect this function to fail.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1,WDDM 1.3 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tile_region_size.md">D3DWDDM1_3DDI_TILE_REGION_SIZE</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_tile_copy_flag.md">D3DWDDM1_3DDI_TILE_COPY_FLAG</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_tiled_resource_coordinate.md">D3DWDDM1_3DDI_TILED_RESOURCE_COORDINATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM1_3DDI_COPYTILES callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>