---
UID: NS:d3dumddi._D3DDDICB_RENDERFLAGS
title: "_D3DDDICB_RENDERFLAGS"
author: windows-driver-content
description: The D3DDDICB_RENDERFLAGS structure identifies information about a command buffer to be rendered.
old-location: display\d3dddicb_renderflags.htm
old-project: display
ms.assetid: 18ae8ec2-a9e9-40e2-8b11-93fd163a801d
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDICB_RENDERFLAGS, D3DDDICB_RENDERFLAGS structure [Display Devices], D3D_other_Structs_559cfa58-5c9b-470e-aa4b-6c145045ed82.xml, _D3DDDICB_RENDERFLAGS, d3dumddi/D3DDDICB_RENDERFLAGS, display.d3dddicb_renderflags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDICB_RENDERFLAGS
product: Windows
targetos: Windows
req.typenames: D3DDDICB_RENDERFLAGS
---

# _D3DDDICB_RENDERFLAGS structure
The D3DDDICB_RENDERFLAGS structure identifies information about a command buffer to be rendered.

## Syntax
````
typedef struct _D3DDDICB_RENDERFLAGS {
  union {
    struct {
      UINT ResizeCommandBuffer  :1;
      UINT ResizeAllocationList  :1;
      UINT ResizePatchLocationList  :1;
      UINT NullRendering  :1;
      UINT Reserved  :28;
    };
    UINT   Value;
  };
} D3DDDICB_RENDERFLAGS;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_render.md">D3DDDICB_RENDER</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_rendercb.md">pfnRenderCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_RENDERFLAGS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>