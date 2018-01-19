---
UID : NS:d3d10umddi.D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW
title : D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW
author : windows-driver-content
description : The D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW structure describes a cube texture that is used to create a render target view in a call to the CreateRenderTargetView function.
old-location : display\d3d10ddiarg_texcube_rendertargetview.htm
old-project : display
ms.assetid : cffd2c5d-847b-4ecd-b99d-5916e7b5bbd0
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW, D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW
req.alt-loc : d3d10umddi.h
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
req.typenames : D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW
---

# D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW structure
The D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW structure describes a cube texture that is used to create a render target view in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a> function.

## Syntax
````
typedef struct D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW {
  UINT MipSlice;
  UINT FirstArraySlice;
  UINT ArraySize;
} D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW;
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
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivaterendertargetviewsize.md">CalcPrivateRenderTargetViewSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createrendertargetview.md">CreateRenderTargetView</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createrendertargetview.md">D3D10DDIARG_CREATERENDERTARGETVIEW</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10DDIARG_TEXCUBE_RENDERTARGETVIEW structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>