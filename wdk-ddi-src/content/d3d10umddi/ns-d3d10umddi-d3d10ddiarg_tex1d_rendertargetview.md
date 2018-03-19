---
UID: NS:d3d10umddi.D3D10DDIARG_TEX1D_RENDERTARGETVIEW
title: D3D10DDIARG_TEX1D_RENDERTARGETVIEW
author: windows-driver-content
description: The D3D10DDIARG_TEX1D_RENDERTARGETVIEW structure describes a one-dimensional (1-D) texture that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location: display\d3d10ddiarg_tex1d_rendertargetview.htm
old-project: display
ms.assetid: 42b0b937-55a3-47c2-9b5b-f9e3859cab71
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10DDIARG_TEX1D_RENDERTARGETVIEW, D3D10DDIARG_TEX1D_RENDERTARGETVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_588779f0-1830-4434-b83e-1f1d8e16906b.xml, d3d10umddi/D3D10DDIARG_TEX1D_RENDERTARGETVIEW, display.d3d10ddiarg_tex1d_rendertargetview
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
-	D3D10DDIARG_TEX1D_RENDERTARGETVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_TEX1D_RENDERTARGETVIEW
---

# D3D10DDIARG_TEX1D_RENDERTARGETVIEW structure
The D3D10DDIARG_TEX1D_RENDERTARGETVIEW structure describes a one-dimensional (1-D) texture that is used to create a render target view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a> function.

## Syntax
````
typedef struct D3D10DDIARG_TEX1D_RENDERTARGETVIEW {
  UINT MipSlice;
  UINT FirstArraySlice;
  UINT ArraySize;
} D3D10DDIARG_TEX1D_RENDERTARGETVIEW;
````

## Members


`MipSlice`

[in] The identifier of the MIP-map slice.

`FirstArraySlice`

[in] The identifier of the first array slice.

`ArraySize`

[in] The number of array slices for the texture.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createrendertargetview.md">D3D10DDIARG_CREATERENDERTARGETVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a>