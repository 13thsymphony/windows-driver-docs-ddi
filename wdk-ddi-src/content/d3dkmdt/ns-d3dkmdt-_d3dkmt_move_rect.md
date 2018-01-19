---
UID : NS:d3dkmdt._D3DKMT_MOVE_RECT
title : _D3DKMT_MOVE_RECT
author : windows-driver-content
description : Provides information on a screen-to-screen move and a dirty rectangle copy operation.
old-location : display\d3dkmt_move_rect.htm
old-project : display
ms.assetid : 2d9e0a8e-9485-427d-bdd0-2d89dec76a77
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _D3DKMT_MOVE_RECT, D3DKMT_MOVE_RECT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmdt.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3DKMT_MOVE_RECT
req.alt-loc : D3dkmdt.h
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
req.typenames : D3DKMT_MOVE_RECT
---

# _D3DKMT_MOVE_RECT structure
Provides information on a screen-to-screen move and a dirty rectangle copy operation.

## Syntax
````
typedef struct _D3DKMT_MOVE_RECT {
  POINT SourcePoint;
  RECT  DestRect;
} D3DKMT_MOVE_RECT;
````

## Members

        
            `DestRect`

            A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that contains the destination rectangle where the dirty rectangle is copied to.
        
            `SourcePoint`

            A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a> structure that describes the source (<i>x, y</i>) point where the source rectangle is copied from.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmdt.h |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569161">POINT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_MOVE_RECT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>