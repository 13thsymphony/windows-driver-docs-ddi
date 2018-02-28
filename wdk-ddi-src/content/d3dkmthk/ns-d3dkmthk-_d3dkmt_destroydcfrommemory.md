---
UID: NS:d3dkmthk._D3DKMT_DESTROYDCFROMMEMORY
title: "_D3DKMT_DESTROYDCFROMMEMORY"
author: windows-driver-content
description: The D3DKMT_DESTROYDCFROMMEMORY structure describes parameters for releasing the display context.
old-location: display\d3dkmt_destroydcfrommemory.htm
old-project: display
ms.assetid: 98110dcc-bd82-444b-80bb-45a989e2f4f1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_DESTROYDCFROMMEMORY, D3DKMT_DESTROYDCFROMMEMORY structure [Display Devices], OpenGL_Structs_1d3adbd5-a0cf-4650-b293-148ca3b093fb.xml, _D3DKMT_DESTROYDCFROMMEMORY, d3dkmthk/D3DKMT_DESTROYDCFROMMEMORY, display.d3dkmt_destroydcfrommemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_DESTROYDCFROMMEMORY
product: Windows
targetos: Windows
req.typenames: D3DKMT_DESTROYDCFROMMEMORY
---

# _D3DKMT_DESTROYDCFROMMEMORY structure
The D3DKMT_DESTROYDCFROMMEMORY structure describes parameters for releasing the display context.

## Syntax
````
typedef struct _D3DKMT_DESTROYDCFROMMEMORY {
  HDC    hDc;
  HANDLE hBitmap;
} D3DKMT_DESTROYDCFROMMEMORY;
````

## Members


`hBitmap`

[in] A handle to a bitmap that is related to the display context.

`hDc`

[in] A handle to the display context.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroydcfrommemory.md">D3DKMTDestroyDCFromMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DESTROYDCFROMMEMORY structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>