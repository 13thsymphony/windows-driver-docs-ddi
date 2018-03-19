---
UID: NS:d3dkmthk._D3DKMT_GETDISPLAYMODELIST
title: "_D3DKMT_GETDISPLAYMODELIST"
author: windows-driver-content
description: The D3DKMT_GETDISPLAYMODELIST structure describes a list of display modes.
old-location: display\d3dkmt_getdisplaymodelist.htm
old-project: display
ms.assetid: c937f1df-0221-4418-b48a-bcf0c41fa1e0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_GETDISPLAYMODELIST, D3DKMT_GETDISPLAYMODELIST structure [Display Devices], OpenGL_Structs_27c1c3f3-6316-4dc3-b83d-1a8f6f6360bb.xml, _D3DKMT_GETDISPLAYMODELIST, d3dkmthk/D3DKMT_GETDISPLAYMODELIST, display.d3dkmt_getdisplaymodelist
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
-	D3DKMT_GETDISPLAYMODELIST
product: Windows
targetos: Windows
req.typenames: D3DKMT_GETDISPLAYMODELIST
---

# _D3DKMT_GETDISPLAYMODELIST structure
The D3DKMT_GETDISPLAYMODELIST structure describes a list of display modes.

## Syntax
````
typedef struct _D3DKMT_GETDISPLAYMODELIST {
  D3DKMT_HANDLE                  hAdapter;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DKMT_DISPLAYMODE             *pModeList;
  UINT                           ModeCount;
} D3DKMT_GETDISPLAYMODELIST;
````

## Members


`hAdapter`

[in] A handle to the graphics adapter.

`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology that the display modes apply to.

`pModeList`

[out] An array of <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_displaymode.md">D3DKMT_DISPLAYMODE</a> structures that represent the list of display modes.

`ModeCount`

[in/out] The number of display modes in the array that <b>pModeList</b> specifies.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetdisplaymodelist.md">D3DKMTGetDisplayModeList</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_displaymode.md">D3DKMT_DISPLAYMODE</a>