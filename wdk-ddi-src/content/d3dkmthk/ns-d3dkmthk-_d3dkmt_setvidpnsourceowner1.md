---
UID: NS:d3dkmthk._D3DKMT_SETVIDPNSOURCEOWNER1
title: "_D3DKMT_SETVIDPNSOURCEOWNER1"
author: windows-driver-content
description: Describes the information, including output duplication options, needed to set or release the video present source in the path of a video present network (VidPN) topology that owns the VidPN.
old-location: display\d3dkmt_setvidpnsourceowner1.htm
old-project: display
ms.assetid: 3148c628-60e3-47a8-bae1-e33390af7e33
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_SETVIDPNSOURCEOWNER1, D3DKMT_SETVIDPNSOURCEOWNER1 structure [Display Devices], _D3DKMT_SETVIDPNSOURCEOWNER1, d3dkmthk/D3DKMT_SETVIDPNSOURCEOWNER1, display.d3dkmt_setvidpnsourceowner1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmthk.h
api_name:
-	D3DKMT_SETVIDPNSOURCEOWNER1
product: Windows
targetos: Windows
req.typenames: D3DKMT_SETVIDPNSOURCEOWNER1
---

# _D3DKMT_SETVIDPNSOURCEOWNER1 structure
Describes the information, including output duplication options, needed to set or release the video present source in the path of a video present network (VidPN) topology that owns the VidPN.

## Syntax
````
typedef struct _D3DKMT_SETVIDPNSOURCEOWNER1 {
  D3DKMT_SETVIDPNSOURCEOWNER    Version0;
  D3DKMT_VIDPNSOURCEOWNER_FLAGS Flags;
} D3DKMT_SETVIDPNSOURCEOWNER1;
````

## Members


`Version0`

A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a> structure that contains information needed to set or release the video present source.

`Flags`

A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_vidpnsourceowner_flags.md">D3DKMT_VIDPNSOURCEOWNER_FLAGS</a> structure that specifies output duplication options.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_setvidpnsourceowner.md">D3DKMT_SETVIDPNSOURCEOWNER</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_vidpnsourceowner_flags.md">D3DKMT_VIDPNSOURCEOWNER_FLAGS</a>