---
UID: NS:d3dkmthk._D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
title: "_D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT"
author: windows-driver-content
description: The D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source.
old-location: display\d3dkmt_setdisplayprivatedriverformat.htm
old-project: display
ms.assetid: a99a3b15-8c91-4aef-a82c-665c8494fa57
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT, D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure [Display Devices], OpenGL_Structs_c5440fbe-47f2-43eb-ae09-e9295bfa4bad.xml, _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT, d3dkmthk/D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT, display.d3dkmt_setdisplayprivatedriverformat
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
-	D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
product: Windows
targetos: Windows
req.typenames: D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT
---

# _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure
The D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source.

## Syntax
````
typedef struct _D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT {
  D3DKMT_HANDLE                  hDevice;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  UINT                           PrivateDriverFormatAttribute;
} D3DKMT_SETDISPLAYPRIVATEDRIVERFORMAT;
````

## Members


`hDevice`

[in] A handle to the device that requests to change the private-format attribute of a video present source.

`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to set a private-format attribute on (that is, the identifier of the primary surface to set a private-format attribute on).

`PrivateDriverFormatAttribute`

[in] A UINT value that specifies the private-format attribute to set for the video present source that the <b>VidPnSourceId</b> member specifies.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetdisplayprivatedriverformat.md">D3DKMTSetDisplayPrivateDriverFormat</a>