---
UID: NS:d3dumddi._D3DDDICB_CREATEOVERLAY
title: "_D3DDDICB_CREATEOVERLAY"
author: windows-driver-content
description: The D3DDDICB_CREATEOVERLAY structure describes overlay hardware.
old-location: display\d3dddicb_createoverlay.htm
old-project: display
ms.assetid: 52f95379-7bfd-4606-9199-ea253ccd6f35
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_CREATEOVERLAY, D3DDDICB_CREATEOVERLAY structure [Display Devices], D3D_param_Structs_d6883734-5c4a-480f-bb54-12df15297daa.xml, _D3DDDICB_CREATEOVERLAY, d3dumddi/D3DDDICB_CREATEOVERLAY, display.d3dddicb_createoverlay
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
-	D3DDDICB_CREATEOVERLAY
product: Windows
targetos: Windows
req.typenames: D3DDDICB_CREATEOVERLAY
---

# _D3DDDICB_CREATEOVERLAY structure
The D3DDDICB_CREATEOVERLAY structure describes overlay hardware.

## Syntax
````
typedef struct _D3DDDICB_CREATEOVERLAY {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DDDI_KERNELOVERLAYINFO       OverlayInfo;
  D3DKMT_HANDLE                  hKernelOverlay;
} D3DDDICB_CREATEOVERLAY;
````

## Members


`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to overlay on (that is, the identifier of the primary surface to overlay on).

`OverlayInfo`

[in] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_kerneloverlayinfo.md">D3DDDI_KERNELOVERLAYINFO</a> structure that describes information about the kernel-mode overlay object.

`hKernelOverlay`

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the kernel-mode overlay object. This overlay object represents the overlay hardware in subsequent calls by the user-mode display driver to the Microsoft Direct3D runtime.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_kerneloverlayinfo.md">D3DDDI_KERNELOVERLAYINFO</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a>