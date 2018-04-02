---
UID: NS:d3dumddi._D3DDDICB_CREATECONTEXT
title: "_D3DDDICB_CREATECONTEXT"
author: windows-driver-content
description: The D3DDDICB_CREATECONTEXT structure describes a context to create.
old-location: display\d3dddicb_createcontext.htm
old-project: display
ms.assetid: 6bee57b5-f4b3-424c-aeb5-3bf65ab16392
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDICB_CREATECONTEXT, D3DDDICB_CREATECONTEXT structure [Display Devices], D3D_param_Structs_9ad6c5e1-c3aa-4546-b3c9-c07c8350093b.xml, _D3DDDICB_CREATECONTEXT, d3dumddi/D3DDDICB_CREATECONTEXT, display.d3dddicb_createcontext
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
-	D3DDDICB_CREATECONTEXT
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_CREATECONTEXT
---

# _D3DDDICB_CREATECONTEXT structure
The D3DDDICB_CREATECONTEXT structure describes a context to create.

## Syntax
```
typedef struct _D3DDDICB_CREATECONTEXT {
  UINT                      NodeOrdinal;
  UINT                      EngineAffinity;
  D3DDDI_CREATECONTEXTFLAGS Flags;
  VOID                      *pPrivateDriverData;
  UINT                      PrivateDriverDataSize;
  HANDLE                    hContext;
  VOID                      *pCommandBuffer;
  UINT                      CommandBufferSize;
  D3DDDI_ALLOCATIONLIST     *pAllocationList;
  UINT                      AllocationListSize;
  D3DDDI_PATCHLOCATIONLIST  *pPatchLocationList;
  UINT                      PatchLocationListSize;
  D3DGPU_VIRTUAL_ADDRESS    CommandBuffer;
} D3DDDICB_CREATECONTEXT;
```

## Members


`NodeOrdinal`

[in] The zero-based index for the node that the context is scheduled on.

`EngineAffinity`

[in] The zero-based index for the engine, within the node that <b>NodeOrdinal</b> specifies, that the context can run in.

`Flags`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544502">D3DDDI_CREATECONTEXTFLAGS</a> structure that indicates, in bit-field flags, how to create the context.

`pPrivateDriverData`

[in] A pointer to private data that is passed to a display miniport driver.

`PrivateDriverDataSize`

[in] The size, in bytes, of the private data that <b>pPrivateDriverData</b> points to.

`hContext`

[out] A handle to the context that the <a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a> function creates.

`pCommandBuffer`

[out] A pointer to the first command buffer for the created context.

`CommandBufferSize`

[out] The size, in bytes, of the first command buffer for the created context, which <b>pCommandBuffer</b> points to.

`pAllocationList`

[out] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544375">D3DDDI_ALLOCATIONLIST</a> structures for the first allocation list for the created context.

`AllocationListSize`

[out] The number of elements in the allocation-list array that <b>pAllocationList</b> specifies.

`pPatchLocationList`

[out] An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a> structures for the first patch-location list for the created context.

`PatchLocationListSize`

[out] The number of elements in the patch-location-list array that <b>pPatchLocationList</b> specifies.

`CommandBuffer`

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544375">D3DDDI_ALLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544502">D3DDDI_CREATECONTEXTFLAGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/f3f5d6bc-3bc6-4214-830a-cffff01069cc">pfnCreateContextCb</a>