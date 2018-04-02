---
UID: NS:d3dumddi._D3DDDICB_DESTROYCONTEXT
title: "_D3DDDICB_DESTROYCONTEXT"
author: windows-driver-content
description: The D3DDDICB_DESTROYCONTEXT structure contains the handle to a context to destroy.
old-location: display\d3dddicb_destroycontext.htm
old-project: display
ms.assetid: 31f1577d-72ba-495a-97e4-0569bdbc0ed7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDICB_DESTROYCONTEXT, D3DDDICB_DESTROYCONTEXT structure [Display Devices], D3D_param_Structs_40e3c0f9-b30b-4fab-8b4a-a1809f03d0ba.xml, _D3DDDICB_DESTROYCONTEXT, d3dumddi/D3DDDICB_DESTROYCONTEXT, display.d3dddicb_destroycontext
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
-	D3DDDICB_DESTROYCONTEXT
product: Windows
targetos: Windows
req.typenames: D3DDDICB_DESTROYCONTEXT
---

# _D3DDDICB_DESTROYCONTEXT structure
The D3DDDICB_DESTROYCONTEXT structure contains the handle to a context to destroy.

## Syntax
```
typedef struct _D3DDDICB_DESTROYCONTEXT {
  HANDLE hContext;
} D3DDDICB_DESTROYCONTEXT;
```

## Members


`hContext`

[in] A handle that the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function returns and that identifies the context to destroy.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>



<a href="https://msdn.microsoft.com/6b65d75b-544b-4153-b821-d59d6f85673d">pfnDestroyContextCb</a>