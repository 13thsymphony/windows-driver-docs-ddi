---
UID : NS:d3dumddi._D3DDDIARG_DISCARD
title : _D3DDDIARG_DISCARD
author : windows-driver-content
description : Defines video display memory that can be discarded because the contents are no longer needed.
old-location : display\d3dddiarg_discard.htm
old-project : display
ms.assetid : 6efee74e-9e82-4631-8360-19061b0c015d
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DDDIARG_DISCARD, D3DDDIARG_DISCARD
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DDDIARG_DISCARD
req.alt-loc : D3dumddi.h
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
req.typenames : D3DDDIARG_DISCARD
---

# _D3DDDIARG_DISCARD structure
Defines video display memory that can be discarded because the contents are no longer needed.

## Syntax
````
typedef struct _D3DDDIARG_DISCARD {
  HANDLE     hResource;
  UINT       FirstSubResource;
  UINT       NumSubResources;
  const RECT *pRects;
  UINT       NumRects;
} D3DDDIARG_DISCARD;
````

## Members

        
            `FirstSubResource`

            The index of the first subresource to be discarded.
        
            `hResource`

            A handle to the resource in which subresources are to be discarded.
        
            `NumRects`

            The number of rectangles in the array that the  <b>pRects</b> member specifies.
        
            `NumSubResources`

            The number of subresources to be discarded.
        
            `pRects`

            An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structures for the rectangles in the resource view to discard. If <b>NULL</b>, the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_discard.md">Discard</a> function discards the entire surface.


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
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_discard.md">Discard</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DISCARD structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>