---
UID: NS:d3dkmthk._D3DKMT_FENCE_PRESENTHISTORYTOKEN
title: "_D3DKMT_FENCE_PRESENTHISTORYTOKEN"
author: windows-driver-content
description: The D3DKMT_FENCE_PRESENTHISTORYTOKEN structure identifies a fence present-history operation.
old-location: display\d3dkmt_fence_presenthistorytoken.htm
old-project: display
ms.assetid: a27371cf-08d2-4502-b766-3b9c60272080
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_FENCE_PRESENTHISTORYTOKEN, D3DKMT_FENCE_PRESENTHISTORYTOKEN structure [Display Devices], OpenGL_Structs_eaaa4933-1089-4698-9812-05ff6521f431.xml, _D3DKMT_FENCE_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_FENCE_PRESENTHISTORYTOKEN, display.d3dkmt_fence_presenthistorytoken
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_FENCE_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system.
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
-	D3DKMT_FENCE_PRESENTHISTORYTOKEN
product: Windows
targetos: Windows
req.typenames: D3DKMT_FENCE_PRESENTHISTORYTOKEN
---

# _D3DKMT_FENCE_PRESENTHISTORYTOKEN structure
The D3DKMT_FENCE_PRESENTHISTORYTOKEN structure identifies a fence present-history operation.

## Syntax
```
typedef struct _D3DKMT_FENCE_PRESENTHISTORYTOKEN {
  UINT64 Key;
} D3DKMT_FENCE_PRESENTHISTORYTOKEN;
```

## Members


`Key`

[in] A 64-bit value that specifies the key for the fence.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DKMT_FENCE_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system. D3DKMT_FENCE_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548188">D3DKMT_PRESENTHISTORYTOKEN</a>