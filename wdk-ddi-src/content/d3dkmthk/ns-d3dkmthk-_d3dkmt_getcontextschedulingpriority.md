---
UID: NS:d3dkmthk._D3DKMT_GETCONTEXTSCHEDULINGPRIORITY
title: "_D3DKMT_GETCONTEXTSCHEDULINGPRIORITY"
author: windows-driver-content
description: The D3DKMT_GETDEVICESCHEDULINGPRIORITY structure describes parameters for retrieving scheduling priority for a device context.
old-location: display\d3dkmt_getcontextschedulingpriority.htm
old-project: display
ms.assetid: ef60ba1c-6fff-4553-ba1c-97abbe48fed9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_GETCONTEXTSCHEDULINGPRIORITY, D3DKMT_GETCONTEXTSCHEDULINGPRIORITY structure [Display Devices], OpenGL_Structs_076cf4c2-d805-473f-a035-1e0ec357ca1e.xml, _D3DKMT_GETCONTEXTSCHEDULINGPRIORITY, d3dkmthk/D3DKMT_GETCONTEXTSCHEDULINGPRIORITY, display.d3dkmt_getcontextschedulingpriority
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
-	D3DKMT_GETCONTEXTSCHEDULINGPRIORITY
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_GETCONTEXTSCHEDULINGPRIORITY
---

# _D3DKMT_GETCONTEXTSCHEDULINGPRIORITY structure
The D3DKMT_GETDEVICESCHEDULINGPRIORITY structure describes parameters for retrieving scheduling priority for a device context.

## Syntax
```
typedef struct _D3DKMT_GETCONTEXTSCHEDULINGPRIORITY {
  D3DKMT_HANDLE hContext;
  INT           Priority;
} D3DKMT_GETCONTEXTSCHEDULINGPRIORITY;
```

## Members


`hContext`

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle to the device context to retrieve scheduling priority for.

`Priority`

[out] The priority level that is retrieved for the device context.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546957">D3DKMTGetContextSchedulingPriority</a>