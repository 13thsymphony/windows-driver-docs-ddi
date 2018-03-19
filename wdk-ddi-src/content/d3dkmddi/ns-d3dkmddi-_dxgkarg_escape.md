---
UID: NS:d3dkmddi._DXGKARG_ESCAPE
title: "_DXGKARG_ESCAPE"
author: windows-driver-content
description: The DXGKARG_ESCAPE structure describes information that the user-mode display driver shares with the display miniport driver.
old-location: display\dxgkarg_escape.htm
old-project: display
ms.assetid: 73a1afa6-e156-4733-b204-a9cae4e18563
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKARG_ESCAPE, DXGKARG_ESCAPE structure [Display Devices], DmStructs_1edfa7aa-7ba1-4abc-a453-253de2a191af.xml, _DXGKARG_ESCAPE, d3dkmddi/DXGKARG_ESCAPE, display.dxgkarg_escape
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_ESCAPE
product: Windows
targetos: Windows
req.typenames: DXGKARG_ESCAPE
---

# _DXGKARG_ESCAPE structure
The DXGKARG_ESCAPE structure describes information that the user-mode display driver shares with the display miniport driver.

## Syntax
````
typedef struct _DXGKARG_ESCAPE {
  HANDLE             hDevice;
  D3DDDI_ESCAPEFLAGS Flags;
  VOID               *pPrivateDriverData;
  UINT               PrivateDriverDataSize;
  HANDLE             hContext;
} DXGKARG_ESCAPE;
````

## Members


`hDevice`

[in] A handle to the display device (graphics context) that was originally passed to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function.

`Flags`

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_escapeflags.md">D3DDDI_ESCAPEFLAGS</a> structure that indicates, in bit-field flags, how to share information.

`pPrivateDriverData`

[in/out] A pointer to a buffer that contains the information that the display miniport driver and the user-mode display driver share.

`PrivateDriverDataSize`

[in/out] The size, in bytes, of the buffer that <b>pPrivateDriverData</b> points to.

`hContext`

[in] A handle to the context that was originally passed to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_escapeflags.md">D3DDDI_ESCAPEFLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_escape.md">DxgkDdiEscape</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>