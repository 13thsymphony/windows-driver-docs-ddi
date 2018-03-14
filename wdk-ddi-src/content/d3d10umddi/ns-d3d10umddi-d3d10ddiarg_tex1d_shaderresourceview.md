---
UID: NS:d3d10umddi.D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW
title: D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW
author: windows-driver-content
description: The D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW structure describes a one-dimensional (1-D) texture that is used to create a shader resource view in a call to the CreateShaderResourceView function.
old-location: display\d3d10ddiarg_tex1d_shaderresourceview.htm
old-project: display
ms.assetid: 5cb10ec9-8496-49d1-b8d0-53d8fe7470c5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW, D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW structure [Display Devices], UMDisplayDriver_Dx10param_Structs_804b8de8-55ba-4a68-ba21-ada239882372.xml, d3d10umddi/D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW, display.d3d10ddiarg_tex1d_shaderresourceview
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
-	D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW
---

# D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW structure
The D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW structure describes a one-dimensional (1-D) texture that is used to create a shader resource view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md">CreateShaderResourceView</a> function.

## Syntax
````
typedef struct D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW {
  UINT MostDetailedMip;
  UINT FirstArraySlice;
  UINT MipLevels;
  UINT ArraySize;
} D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW;
````

## Members


`ArraySize`

[in] The number of array slices for the texture.

`FirstArraySlice`

[in] The identifier of the first array slice.

`MipLevels`

[in] The number of MIP-map levels for the texture.

`MostDetailedMip`

[in] The identifier of the most detailed MIP-map.

## Remarks
If the <b>MipLevels</b> member is set to -1, the MIP-maps in the texture start from the MIP-map that is set in the <b>MostDetailedMip</b> member. 

If the <b>ArraySize</b> member is set to -1, the array slices in the texture start from the array slice that is set in <b>FirstArraySlice</b> member.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshaderresourceviewsize.md">CalcPrivateShaderResourceViewSize</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createshaderresourceview.md">CreateShaderResourceView</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createshaderresourceview.md">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_TEX1D_SHADERRESOURCEVIEW structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>