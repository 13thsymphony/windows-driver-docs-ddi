---
UID: NS:d3d10umddi.D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW
title: D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW
author: windows-driver-content
description: The D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW structure describes a three-dimensional (3-D) texture that is used to create an unordered access view in a call to the CreateUnorderedAccessView function.
old-location: display\d3d11ddiarg_tex3d_unorderedaccessview.htm
old-project: display
ms.assetid: 15b535ab-28ed-41c3-8544-4ccb27a53649
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW, D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_0d8a28d7-9bb4-49b9-9ce9-1f290072ba4d.xml, d3d10umddi/D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW, display.d3d11ddiarg_tex3d_unorderedaccessview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system.
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
-	D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW
---

# D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW structure
The D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW structure describes a three-dimensional (3-D) texture that is used to create an unordered access view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a> function.

## Syntax
````
typedef struct D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW {
  UINT MipSlice;
  UINT FirstW;
  UINT WSize;
} D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW;
````

## Members


`MipSlice`

[in] The identifier of the MIP-map slice.

`FirstW`

[in] The identifier of the first array slice.

`WSize`

[in] The number of array slices for the texture.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system. D3D11DDIARG_TEX3D_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createunorderedaccessview.md">CreateUnorderedAccessView</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview.md">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_calcprivateunorderedaccessviewsize.md">CalcPrivateUnorderedAccessViewSize</a>