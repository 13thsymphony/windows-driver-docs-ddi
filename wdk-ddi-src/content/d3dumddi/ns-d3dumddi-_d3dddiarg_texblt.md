---
UID : NS:d3dumddi._D3DDDIARG_TEXBLT
title : _D3DDDIARG_TEXBLT
author : windows-driver-content
description : The D3DDDIARG_TEXBLT structure describes parameters for a texture bit-block transfer (bitblt) operation.
old-location : display\d3dddiarg_texblt.htm
old-project : display
ms.assetid : e236ac2e-24d7-45a4-aa88-b496c8d92764
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DDDIARG_TEXBLT, D3DDDIARG_TEXBLT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DDDIARG_TEXBLT
req.alt-loc : d3dumddi.h
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
req.typenames : D3DDDIARG_TEXBLT
---

# _D3DDDIARG_TEXBLT structure
The D3DDDIARG_TEXBLT structure describes parameters for a texture bit-block transfer (bitblt) operation.

## Syntax
````
typedef struct _D3DDDIARG_TEXBLT {
  HANDLE hDstResource;
  HANDLE hSrcResource;
  UINT   CubeMapFace;
  POINT  DstPoint;
  RECT   SrcRect;
} D3DDDIARG_TEXBLT;
````

## Members

        
            `CubeMapFace`

            [in] The face of a cube map.
        
            `DstPoint`

            [in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a> structure that describes the destination point where the source texture is copied.
        
            `hDstResource`

            [in] A handle to the destination resource.
        
            `hSrcResource`

            [in] A handle to the source resource.
        
            `SrcRect`

            [in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the source texture to copy to the destination point.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_texblt.md">TexBlt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_TEXBLT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>