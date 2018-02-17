---
UID: NS:d3d10umddi.D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW
title: D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW
author: windows-driver-content
description: The D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW structure describes a one-dimensional texture (1-D) that is used to create a depth stencil view in a call to the CreateDepthStencilView function.
old-location: display\d3d10ddiarg_tex1d_depthstencilview.htm
old-project: display
ms.assetid: 313e616c-12e3-4493-9c49-e79232bbf031
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d10ddiarg_tex1d_depthstencilview, UMDisplayDriver_Dx10param_Structs_5d65c450-41df-45d9-9bdd-9ccb9890161a.xml, D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW, D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW structure [Display Devices], d3d10umddi/D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW
---

# D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW structure
The D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW structure describes a one-dimensional texture (1-D) that is used to create a depth stencil view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilview.md">CreateDepthStencilView</a> function.

## Syntax
````
typedef struct D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW {
  UINT MipSlice;
  UINT FirstArraySlice;
  UINT ArraySize;
} D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW;
````

## Members


`ArraySize`

[in] The number of array slices for the texture.

`FirstArraySlice`

[in] The identifier of the first array slice.

`MipSlice`

[in] The identifier of the MIP-map slice.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdepthstencilview.md">CreateDepthStencilView</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdepthstencilview.md">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatedepthstencilviewsize.md">CalcPrivateDepthStencilViewSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_TEX1D_DEPTHSTENCILVIEW structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>