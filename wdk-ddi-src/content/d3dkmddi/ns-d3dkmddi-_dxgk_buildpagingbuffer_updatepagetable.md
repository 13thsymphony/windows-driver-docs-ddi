---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE
title: "_DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE"
author: windows-driver-content
description: DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE is used as part of a page table update operation.
old-location: display\dxgk_buildpagingbuffer_updatepagetable.htm
old-project: display
ms.assetid: 734B2E28-75F8-49AE-AAAB-EB0C037C6432
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE, DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE, d3dkmddi/DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE, display.dxgk_buildpagingbuffer_updatepagetable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE
product: Windows
targetos: Windows
req.typenames: DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE
---

# _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE structure
<b>DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE</b> is used as part of a page table update operation.

## Syntax
````
typedef struct _DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE {
  UINT                        PageTableLevel;
  HANDLE                      hAllocation;
  DXGK_PAGETABLEUPDATEADDRESS PageTableAddress;
  DXGK_PTE                    *pPageTableEntries;
  UINT                        StartIndex;
  UINT                        NumPageTableEntries;
  UINT                        Reserved0;
  DXGK_UPDATEPAGETABLEFLAGS   Flags;
  UINT64                      DriverProtection;
  UINT64                      AllocationOffsetInBytes;
  HANDLE                      hProcess;
  DXGK_PAGETABLEUPDATEMODE    UpdateMode;
  DXGK_PTE                    *pPageTableEntries64KB;
  D3DGPU_VIRTUAL_ADDRESS      FirstPteVirtualAddress;
} DXGK_BUILDPAGINGBUFFER_UPDATEPAGETABLE;
````

## Members


`AllocationOffsetInBytes`

When <b>hAllocation</b> is non-NULL, this field specifies the relative offset, in bytes, from the beginning of the allocation to the first page being targeted by this update operation. If the update target multiple pages from <b>hAllocation</b>, those pages are guaranteed to be sequential. For example, video memory manager may be updating a GPU virtual address to page 4,5,6,7 in <b>hAllocation</b>. There will never be a case where a driver would see a single update operation which target non sequential pages (ex. 4,5,7). Note that although the pages are guaranteed to be sequential from the point of view of the allocation, they may not be physically contiguous in memory.

`DriverProtection`

Passed by UMD in MapGpuVirtualAddressRangeCb.

`FirstPteVirtualAddress`

The GPU virtual address that is mapped by the first updated page table entry.

`Flags`

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_updatepagetableflags.md">DXGK_UPDATEPAGETABLEFLAGS</a> structure describing the update operation.

`hAllocation`

Kernel mode driver handle of an allocation, which is mapped by the page table entries. The handle is returned by the kernel mode driver from <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>. The handle can be <b>NULL</b> for allocations, which do not have a kernel mode drver   handle (page tables, page directories, etc.).

`hProcess`

Kernel mode driver process handle for the process whose page table entries are updated. This is the value returned from <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md">DxgkDdiCreateProcess</a>.

`NumPageTableEntries`

The number of entries which need to be copied.

`PageTableAddress`

Address of the page table to update. If <b>DXGK_VIRTUALADDRESSCAPS:: PageTableUpdateMode</b> is <b>DXGK_PAGETABLEUPDATE_CPU_VIRTUAL</b>, the CPU virtual address is in the <b>CpuVirtual</b> field. If <b>DXGK_VIRTUALADDRESSCAPS:: PageTableUpdateMode</b> is <b>DXGK_PAGETABLEUPDATE_GPU_VIRTUAL</b>, the GPU virtual address is in the <b>GpuVirtual</b> field. If <b>DXGK_VIRTUALADDRESSCAPS:: PageTableUpdateMode</b> is <b>DXGK_PAGETABLEUPDATE_GPU_PHYSICAL</b>, the GPU physical address is in the <b>GpuPhysical</b> field.

`PageTableLevel`

Level of a page table, which is updated.

`pPageTableEntries`

The entries which need to be copied. The index zero in the <b>pPageTableEntries</b> array corresponds to the <b>StartIndex</b> in the driver page table entry array.

`pPageTableEntries64KB`

The entries which need to be copied from the 64KB page tables. The index zero in the <b>pPageTableEntries</b> array corresponds to the <b>StartIndex</b> in the driver page table entry array. The array should be use only when the <b>DXGK_GPUMMUCAPS::DualPteSupported</b> cap is set.

`Reserved0`

This member is reserved and should be set to zero.

`StartIndex`

The starting index of a page table entry within the page table where the entries should be copied. The page table entry array index is zero-based.

`UpdateMode`

Defines the meaning of <b>PageTableAddress</b>. When initializing page tables for the paging process, the update mode is always <b>DXGK_PAGETABLEUPDATE_CPU_VIRTUAL</b> and <b>pDmaBuffer</b> is set to <b>NULL</b>. In this case the driver must update page tables immediately. In other cases the <b>UpdateMode</b> is set to the value, which is specified in <b>DXGK_VIRTUALADDRESSCAPS::GpuMmu.PageTableUpdateMode</b>.

When updating page table entries for a leaf page table, video memory manager assumes that each entry covers a 4KB page. If a GPU page is bigger (4 KB * 2n), the video memory manager will provide entries in the array, which point within GPU pages. The kernel mode driver might only need to initialize page table entries, which point to the beginning of GPU pages. The following figure illustrates this for the case when GPU page is 16 KB.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |