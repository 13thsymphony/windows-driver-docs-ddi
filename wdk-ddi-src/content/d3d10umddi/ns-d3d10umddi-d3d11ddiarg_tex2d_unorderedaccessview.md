---
UID: NS:d3d10umddi.D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW
title: D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW
author: windows-driver-content
description: The D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW structure describes a two-dimensional texture (2-D) that is used to create an unordered access view in a call to the CreateUnorderedAccessView function.
old-location: display\d3d11ddiarg_tex2d_unorderedaccessview.htm
old-project: display
ms.assetid: 2d6a5945-5e30-404c-8ddb-13be781da1b4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW, D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW structure [Display Devices], UMDisplayDriver_Dx11param_Structs_ca281413-3ae7-472c-acd6-76c8ef97b713.xml, d3d10umddi/D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW, display.d3d11ddiarg_tex2d_unorderedaccessview
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system.
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
-	D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW
product: Windows
targetos: Windows
req.typenames: D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW
---

# D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW structure
The D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW structure describes a two-dimensional texture (2-D) that is used to create an unordered access view in a call to the <a href="https://msdn.microsoft.com/c5a258e7-6645-46bb-ab2c-a1c8f5e593b7">CreateUnorderedAccessView</a> function.

## Syntax
```
typedef struct D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW {
  UINT MipSlice;
  UINT FirstArraySlice;
  UINT ArraySize;
};
```

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
| **Windows version** | D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system. D3D11DDIARG_TEX2D_UNORDEREDACCESSVIEW is supported beginning with the Windows 7 operating system. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/6aca5d33-c8c6-4c6b-a66a-e28a958cbc2e">CalcPrivateUnorderedAccessViewSize</a>



<a href="https://msdn.microsoft.com/c5a258e7-6645-46bb-ab2c-a1c8f5e593b7">CreateUnorderedAccessView</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542086">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>