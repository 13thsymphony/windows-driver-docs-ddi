---
UID: NS:d3dkmthk._D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
title: "_D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP"
author: windows-driver-content
description: The D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure describes the parameters to determine the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN.
old-location: display\d3dkmt_checkvidpnexclusiveownership.htm
old-project: display
ms.assetid: 5a7f05a0-11ae-49ed-9015-f2712cc77880
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP, D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure [Display Devices], OpenGL_Structs_23afa7dd-8aaa-402b-9b99-235be17cd26e.xml, _D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP, d3dkmthk/D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP, display.d3dkmt_checkvidpnexclusiveownership
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP is supported beginning with the Windows 7 operating system.
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
-	D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP
---

# _D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure
The D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP structure describes the parameters to determine the video present source in the path of a video present network (VidPN) topology that exclusively owns the VidPN.

## Syntax
```
typedef struct _D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP {
  D3DKMT_HANDLE                  hAdapter;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
} D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP;
```

## Members


`hAdapter`

[in] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the graphics adapter.

`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to check about.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP is supported beginning with the Windows 7 operating system. D3DKMT_CHECKVIDPNEXCLUSIVEOWNERSHIP is supported beginning with the Windows 7 operating system. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546779">D3DKMTCheckVidPnExclusiveOwnership</a>