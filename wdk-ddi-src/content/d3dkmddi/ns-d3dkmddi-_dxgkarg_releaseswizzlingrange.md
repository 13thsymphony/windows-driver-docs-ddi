---
UID: NS:d3dkmddi._DXGKARG_RELEASESWIZZLINGRANGE
title: "_DXGKARG_RELEASESWIZZLINGRANGE"
author: windows-driver-content
description: The DXGKARG_RELEASESWIZZLINGRANGE structure describes parameters for releasing a swizzling range.
old-location: display\dxgkarg_releaseswizzlingrange.htm
old-project: display
ms.assetid: f7d1af11-c360-4f7f-a47a-cf7a182b2b78
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKARG_RELEASESWIZZLINGRANGE, DXGKARG_RELEASESWIZZLINGRANGE structure [Display Devices], DmStructs_7ed7a86e-7376-47a8-8198-9c991005fd0a.xml, _DXGKARG_RELEASESWIZZLINGRANGE, d3dkmddi/DXGKARG_RELEASESWIZZLINGRANGE, display.dxgkarg_releaseswizzlingrange
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
-	DXGKARG_RELEASESWIZZLINGRANGE
product: Windows
targetos: Windows
req.typenames: DXGKARG_RELEASESWIZZLINGRANGE
---

# _DXGKARG_RELEASESWIZZLINGRANGE structure
The DXGKARG_RELEASESWIZZLINGRANGE structure describes parameters for releasing a swizzling range.

## Syntax
```
typedef struct _DXGKARG_RELEASESWIZZLINGRANGE {
  HANDLE hAllocation;
  UINT   PrivateDriverData;
  UINT   RangeId;
} DXGKARG_RELEASESWIZZLINGRANGE;
```

## Members


`hAllocation`

[in] A handle to the allocation that the display miniport driver assigns and that is returned through the driver's <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function.

`PrivateDriverData`

[in] The 32 bits of private data that the user-mode display driver sent when the display miniport driver's <a href="https://msdn.microsoft.com/f861e055-70db-4e0a-9c62-87e2d41f92ae">DxgkDdiAcquireSwizzlingRange</a> function was called to acquire the swizzling range.

`RangeId`

[in] The zero-based identifier of the swizzling range that the <a href="https://msdn.microsoft.com/6c583a48-baa4-429f-b2fc-5f86859617cc">DxgkDdiReleaseSwizzlingRange</a> function releases.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/f861e055-70db-4e0a-9c62-87e2d41f92ae">DxgkDdiAcquireSwizzlingRange</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/6c583a48-baa4-429f-b2fc-5f86859617cc">DxgkDdiReleaseSwizzlingRange</a>