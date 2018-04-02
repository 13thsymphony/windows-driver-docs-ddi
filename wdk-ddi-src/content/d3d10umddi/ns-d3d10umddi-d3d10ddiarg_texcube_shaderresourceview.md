---
UID: NS:d3d10umddi.D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW
title: D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW
author: windows-driver-content
description: The D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure describes a cube texture that is used to create a shader resource view in a call to the CreateShaderResourceView function.
old-location: display\d3d10ddiarg_texcube_shaderresourceview.htm
old-project: display
ms.assetid: ef45c368-37b9-4208-81d3-1ecab81268b0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW, D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_69378946-808a-4eb0-bca1-25bd4780405d.xml, d3d10umddi/D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW, display.d3d10ddiarg_texcube_shaderresourceview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d10umddi.h
api_name:
-	D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW
---

# D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure
The D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW structure describes a cube texture that is used to create a shader resource view in a call to the <a href="https://msdn.microsoft.com/3b1c998d-3fde-4712-ba74-7c8033033182">CreateShaderResourceView</a> function.

## Syntax
```
typedef struct D3D10DDIARG_TEXCUBE_SHADERRESOURCEVIEW {
  UINT MostDetailedMip;
  UINT MipLevels;
};
```

## Members


`MostDetailedMip`

[in] The identifier of the most detailed MIP-map.

`MipLevels`

[in] The number of MIP-map levels for the texture.

## Remarks
If the <b>MipLevels</b> member is set to -1, the MIP-maps in the texture start from the MIP-map that is set in the <b>MostDetailedMip</b> member.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/2abf5ca9-974b-40d7-b71c-43c4fb33dd7c">CalcPrivateShaderResourceViewSize</a>



<a href="https://msdn.microsoft.com/3b1c998d-3fde-4712-ba74-7c8033033182">CreateShaderResourceView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541708">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>