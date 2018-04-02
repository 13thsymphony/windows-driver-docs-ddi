---
UID: NC:d3dkmddi.DXGKDDI_RELEASESWIZZLINGRANGE
title: DXGKDDI_RELEASESWIZZLINGRANGE
author: windows-driver-content
description: The DxgkDdiReleaseSwizzlingRange function releases a swizzling range that the DxgkDdiAcquireSwizzlingRange function previously set up.
old-location: display\dxgkddireleaseswizzlingrange.htm
old-project: display
ms.assetid: 6c583a48-baa4-429f-b2fc-5f86859617cc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_RELEASESWIZZLINGRANGE, DmFunctions_7dab2ff4-4f37-4b56-a15c-29dcf54f8b8d.xml, DxgkDdiReleaseSwizzlingRange, DxgkDdiReleaseSwizzlingRange callback function [Display Devices], d3dkmddi/DxgkDdiReleaseSwizzlingRange, display.dxgkddireleaseswizzlingrange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiReleaseSwizzlingRange
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_RELEASESWIZZLINGRANGE callback function
The <i>DxgkDdiReleaseSwizzlingRange</i> function releases a swizzling range that the <a href="https://msdn.microsoft.com/f861e055-70db-4e0a-9c62-87e2d41f92ae">DxgkDdiAcquireSwizzlingRange</a> function previously set up.

## Syntax

```
DXGKDDI_RELEASESWIZZLINGRANGE DxgkddiReleaseswizzlingrange;

NTSTATUS DxgkddiReleaseswizzlingrange(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_RELEASESWIZZLINGRANGE pReleaseSwizzlingRange
)
{...}
```

## Parameters

`hAdapter`

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.

`pReleaseSwizzlingRange`

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557644">DXGKARG_RELEASESWIZZLINGRANGE</a> structure that contains information for releasing the swizzling range.


## Return Value

<i>DxgkDdiReleaseSwizzlingRange</i> returns STATUS_SUCCESS, or an appropriate error result if the swizzling range is not successfully released.

## Remarks

The <i>DxgkDdiReleaseSwizzlingRange</i> function is typically called when the specified allocation (that is, the <b>hAllocation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557644">DXGKARG_RELEASESWIZZLINGRANGE</a> structure that the <i>pReleaseSwizzlingRange</i> parameter points to) is evicted or destroyed, or when another allocation requires the swizzling range that the <b>RangeId</b> member of DXGKARG_RELEASESWIZZLINGRANGE specifies.

If the specified allocation is currently associated with multiple swizzling ranges (through calls to the <a href="https://msdn.microsoft.com/f861e055-70db-4e0a-9c62-87e2d41f92ae">DxgkDdiAcquireSwizzlingRange</a> function), the display miniport driver should release only the swizzling range that the <b>RangeId</b> member of DXGKARG_RELEASESWIZZLINGRANGE specifies. If the display miniport driver releases all of the swizzling ranges that are associated with the allocation, random corruption in the allocation might result because an application might currently be using one or more of the swizzling ranges.

The driver must use memory-mapped I/O (MMIO) to set up a swizzling range. These swizzling-range accesses must not interfere with the execution of the GPU (that is, the GPU must not be idle when <i>DxgkDdiReleaseSwizzlingRange</i> is called). 

All calls to <i>DxgkDdiReleaseSwizzlingRange</i> are serialized among themselves but not with any other device driver interface (DDI) function.

<i>DxgkDdiReleaseSwizzlingRange</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557644">DXGKARG_RELEASESWIZZLINGRANGE</a>



<a href="https://msdn.microsoft.com/f861e055-70db-4e0a-9c62-87e2d41f92ae">DxgkDdiAcquireSwizzlingRange</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>