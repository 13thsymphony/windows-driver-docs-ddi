---
UID: NS:d3dkmthk._D3DKMT_DESTROYCONTEXT
title: "_D3DKMT_DESTROYCONTEXT"
author: windows-driver-content
description: The D3DKMT_DESTROYCONTEXT structure contains a handle to a kernel-mode device context to release.
old-location: display\d3dkmt_destroycontext.htm
old-project: display
ms.assetid: 116c0fa7-ac3c-4a56-804c-637514a19c73
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_DESTROYCONTEXT, D3DKMT_DESTROYCONTEXT structure [Display Devices], OpenGL_Structs_97f52665-09e6-4f11-b2cc-a7abcc61827c.xml, _D3DKMT_DESTROYCONTEXT, d3dkmthk/D3DKMT_DESTROYCONTEXT, display.d3dkmt_destroycontext
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
-	D3DKMT_DESTROYCONTEXT
product: Windows
targetos: Windows
req.typenames: D3DKMT_DESTROYCONTEXT
---

# _D3DKMT_DESTROYCONTEXT structure
The D3DKMT_DESTROYCONTEXT structure contains a handle to a kernel-mode device context to release.

## Syntax
````
typedef struct _D3DKMT_DESTROYCONTEXT {
  D3DKMT_HANDLE hContext;
} D3DKMT_DESTROYCONTEXT;
````

## Members


`hContext`

[in] A handle to the device context that the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) supplied and that is returned from the call to the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatecontext.md">D3DKMTCreateContext</a> function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtdestroycontext.md">D3DKMTDestroyContext</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtcreatecontext.md">D3DKMTCreateContext</a>