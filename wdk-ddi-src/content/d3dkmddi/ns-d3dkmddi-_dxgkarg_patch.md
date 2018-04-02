---
UID: NS:d3dkmddi._DXGKARG_PATCH
title: "_DXGKARG_PATCH"
author: windows-driver-content
description: The DXGKARG_PATCH structure describes a direct memory access (DMA) buffer that requires patching (that is, requires the assignment of physical addresses).
old-location: display\dxgkarg_patch.htm
old-project: display
ms.assetid: 37ca2208-253c-417e-a44c-fd1303d5f3dc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKARG_PATCH, DXGKARG_PATCH structure [Display Devices], DmStructs_1fd78713-859f-4584-a696-e89976b58ab7.xml, _DXGKARG_PATCH, d3dkmddi/DXGKARG_PATCH, display.dxgkarg_patch
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
-	DXGKARG_PATCH
product: Windows
targetos: Windows
req.typenames: DXGKARG_PATCH
---

# _DXGKARG_PATCH structure
The DXGKARG_PATCH structure describes a direct memory access (DMA) buffer that requires patching (that is, requires the assignment of physical addresses).

## Syntax
```
typedef struct _DXGKARG_PATCH {
  union {
    HANDLE hContext;
    HANDLE hDevice;
  };
  UINT                           DmaBufferSegmentId;
  PHYSICAL_ADDRESS               DmaBufferPhysicalAddress;
  VOID                           *pDmaBuffer;
  UINT                           DmaBufferSize;
  UINT                           DmaBufferSubmissionStartOffset;
  UINT                           DmaBufferSubmissionEndOffset;
  VOID                           *pDmaBufferPrivateData;
  UINT                           DmaBufferPrivateDataSize;
  UINT                           DmaBufferPrivateDataSubmissionStartOffset;
  UINT                           DmaBufferPrivateDataSubmissionEndOffset;
  CONST DXGK_ALLOCATIONLIST      *pAllocationList;
  UINT                           AllocationListSize;
  CONST D3DDDI_PATCHLOCATIONLIST *pPatchLocationList;
  UINT                           PatchLocationListSize;
  UINT                           PatchLocationListSubmissionStart;
  UINT                           PatchLocationListSubmissionLength;
  UINT                           SubmissionFenceId;
  DXGK_PATCHFLAGS                Flags;
  UINT                           EngineOrdinal;
} DXGKARG_PATCH;
```

## Members


`DmaBufferSegmentId`

[in] The identifier of the memory segment that the DMA buffer was paged in. 

The identifier can be zero if the driver indicated not to map the DMA buffer into the segment by setting the <b>DmaBufferSegmentSet</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561019">DXGK_CONTEXTINFO</a> structure to 0 in a call to the driver's <a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a> function. If <b>DmaBufferSegmentId</b> is zero, the DMA buffer was allocated as a contiguous block of system memory.

`DmaBufferPhysicalAddress`

[in] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the physical address where the DMA buffer was paged in. 

If <b>DmaBufferSegmentId</b> is zero, <b>DmaBufferPhysicalAddress</b> is the physical address in system memory where the DMA buffer is located. 

If <b>DmaBufferSegmentId</b> is nonzero, <b>DmaBufferPhysicalAddress</b> is the segment physical address for the DMA buffer (that is, DXGK_SEGMENTDESCRIPTOR.BaseAddress + DmaBuffer.SegmentOffset). 

Note that <b>DmaBufferPhysicalAddress</b> always refers to the beginning of the DMA buffer even though the driver might be required to patch or submit a section of the DMA buffer that does not include the beginning of the DMA buffer (that is, if the <b>DmaBufferSubmissionStartOffset</b> member is nonzero).

`pDmaBuffer`

[in] A pointer to the start of the DMA buffer (that is, the virtual address of the beginning of the DMA buffer).

`DmaBufferSize`

[in] The size, in bytes, of the DMA buffer that <b>pDmaBuffer</b> points to.

Note that <b>DmaBufferSize</b> represents the entire length of the DMA buffer; however, the request to patch or submit might refer to only a portion of the DMA buffer.

`DmaBufferSubmissionStartOffset`

[in] The offset, in bytes, from the beginning of the DMA buffer that <b>pDmaBuffer</b> specifies to the start of the portion of the DMA buffer that requires patching or submitting. The offset that is received at patch time matches the offset that is received at submission time.

`DmaBufferSubmissionEndOffset`

[in] The offset, in bytes, from the beginning of the DMA buffer that <b>pDmaBuffer</b> specifies to the end of the portion of the DMA buffer that requires patching or submitting. The offset that is received at patch time matches the offset that is received at submission time.

`pDmaBufferPrivateData`

[in] A pointer to the driver-resident private data that is associated with the DMA buffer that <b>pDmaBuffer</b> points to. 

For paging operations, a single paging buffer is used for multiple independent submissions. In that scenario, the driver can indicate—by returning the appropriate private driver data pointer in a call to its <a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a> function—to have either a single driver private data range for all submissions or one for each submission.

`DmaBufferPrivateDataSize`

[in] The size, in bytes, of the private driver data at <b>pDmaBufferPrivateData</b>.

Note that <b>DmaBufferPrivateDataSize</b> represents the entire length of the private driver data buffer; however, the portion that is associated with the current submission might be smaller.

`DmaBufferPrivateDataSubmissionStartOffset`

[in] The offset, in bytes, from the beginning of the DMA buffer private data that <b>pDmaBufferPrivateData</b> specifies to the start of the portion of the private data that is associated with the current submission. <b>DmaBufferPrivateDataSubmissionStartOffset</b> is always zero for a nonpaging request.

`DmaBufferPrivateDataSubmissionEndOffset`

[in] The offset, in bytes, from the beginning of the DMA buffer private data that <b>pDmaBufferPrivateData</b> specifies to the end of the portion of the private data that is associated with the current submission.

`pAllocationList`

[in] A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560975">DXGK_ALLOCATIONLIST</a> structures for the list of allocations that is associated with the DMA buffer that <b>pDmaBuffer</b> points to. 

For paging operations, <b>pAllocationList</b> is <b>NULL</b> because paging buffers are not associated with allocation lists.

`AllocationListSize`

[in] The number of elements in the array that <b>pAllocationList</b> specifies.

Note that <b>AllocationListSize</b> represents the total size of the allocation list; however, the portion of the allocation list that is associated with the current submission might be smaller. 

Note that for paging operations <b>AllocationListSize</b> is zero because paging buffers are not associated with allocation lists.

`pPatchLocationList`

[in] A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a> structures for the list of patch locations that is associated with the DMA buffer that <b>pDmaBuffer</b> points to.

Note that the array can begin with an element that is before the range that is used to patch the DMA buffer.

For paging operations, <b>pPatchLocationList</b> is <b>NULL</b> because paging buffers are not associated with patch-location lists.

`PatchLocationListSize`

[in] The number of elements in the array that <b>pPatchLocationList</b> specifies.

Note that <b>PatchLocationListSize</b> represents the total size of the patch-location list; however, the range that the driver must process is typically smaller. 

For paging operations, <b>PatchLocationListSize</b> is zero because paging buffers are not associated with patch-location lists.

`PatchLocationListSubmissionStart`

[in] The index of the first element in the patch-location list that <b>pPatchLocationList</b> specifies that must be processed. 

For paging operations, <b>PatchLocationListSubmissionStart</b> is zero.

`PatchLocationListSubmissionLength`

[in] The number of elements in the patch-location list that <b>pPatchLocationList</b> specifies that must be processed.

For paging operations, <b>PatchLocationListSubmissionLength</b> is zero.

`SubmissionFenceId`

[in] A unique identifier that the driver can write into the fence command at the end of the DMA buffer. For more information about this type of identifier, see <a href="https://msdn.microsoft.com/0ec8a4eb-c441-47ae-b5de-d86e6065ffd4">Supplying Fence Identifiers</a>.

`Flags`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561992">DXGK_PATCHFLAGS</a> structure that identifies information about the DMA buffer that requires patching.

`EngineOrdinal`

[in] Reserved for future use.

## Remarks
The display miniport driver returns an array in the <b>pAllocationList</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557618">DXGKARG_PRESENT</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff557648">DXGKARG_RENDER</a> structure from its <a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a> or <a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a> function after it translates the command buffer to a direct memory access (DMA) buffer. The video memory manager assigns physical addresses to the <b>PhysicalAddress</b> members of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560975">DXGK_ALLOCATIONLIST</a> structures in the array and passes this array to the driver's <a href="https://msdn.microsoft.com/363be784-0e3b-4f9a-a643-80857478bbae">DxgkDdiPatch</a> function. <b>DxgkDdiPatch</b> patches places in the DMA buffer with these physical addresses.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544630">D3DDDI_PATCHLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557618">DXGKARG_PRESENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557648">DXGKARG_RENDER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560975">DXGK_ALLOCATIONLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561019">DXGK_CONTEXTINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561992">DXGK_PATCHFLAGS</a>



<a href="https://msdn.microsoft.com/d315ff53-4a9f-46a3-ad74-d65a5eb72de1">DxgkDdiBuildPagingBuffer</a>



<a href="https://msdn.microsoft.com/aea21a36-f3d5-4541-bd2d-aa026668c562">DxgkDdiCreateContext</a>



<a href="https://msdn.microsoft.com/363be784-0e3b-4f9a-a643-80857478bbae">DxgkDdiPatch</a>



<a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a>



<a href="https://msdn.microsoft.com/fd634768-5e1e-4f40-82fd-5ef69148c3d7">DxgkDdiRender</a>