---
UID: NS:d3dkmddi._DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL
title: "_DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL"
author: windows-driver-content
description: DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL is used as part of an allocation transfer operation.
old-location: display\dxgk_buildpagingbuffer_transfervirtual.htm
old-project: display
ms.assetid: D4427E44-204F-490C-9EE7-BBC4906E5920
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL, DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL structure [Display Devices], _DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL, d3dkmddi/DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL, display.dxgk_buildpagingbuffer_transfervirtual
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
-	DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL
product:
- Windows
targetos: Windows
req.typenames: DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL
---

# _DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL structure
<b>DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL</b> is used as part of an allocation transfer operation.

## Syntax
```
typedef struct _DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL {
  HANDLE                         hAllocation;
  UINT64                         AllocationOffsetInBytes;
  UINT64                         TransferSizeInBytes;
  D3DGPU_VIRTUAL_ADDRESS         SourceVirtualAddress;
  D3DGPU_VIRTUAL_ADDRESS         DestinationVirtualAddress;
  D3DGPU_VIRTUAL_ADDRESS         SourcePageTable;
  DXGK_MEMORY_TRANSFER_DIRECTION TransferDirection;
  DXGK_TRANSFERVIRTUALFLAGS      Flags;
  D3DGPU_VIRTUAL_ADDRESS         DestinationPageTable;
} DXGK_BUILDPAGINGBUFFER_TRANSFERVIRTUAL;
```

## Members


`hAllocation`

Kernel mode driver handle of the transferred allocation content. The handle is returned from <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>. The allocation properties are needed to perform special transfers (as swizzle, de-swizzle, etc.).

`AllocationOffsetInBytes`

The offset in bytes from the start of the allocation being transferred. The offset should not be added to <b>SourceVirtualAddress</b> or <b>DesinationVirtualAddress</b>.

`TransferSizeInBytes`

The number of bytes to transfer.

`SourceVirtualAddress`

The virtual address of the source in the context of the paging process.

`DestinationVirtualAddress`

The virtual address of the destination in the context of the paging process.

`SourcePageTable`

The GPU virtual address of the page table that is used to map the <b>SourceVirtualAddress</b> address. 

<div class="alert"><b>Note</b>  The address is valid only when the <b>DXGK_GPUMMUCAPS.LegacyBehaviors.SourcePageTableVaInTransfer</b> cap is set.</div>
<div> </div>

`TransferDirection`

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn906830">DXGK_MEMORY_TRANSFER_DIRECTION</a> structure describing the operation.

`Flags`

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn906843">DXGK_TRANSFERVIRTUALFLAGS</a> structure describing the operation.

`DestinationPageTable`

The GPU virtual address of the page table that  is used to map the <b>DestinationVirtualAddress</b> address. The address is valid only when the <b>DXGK_GPUMMUCAPS.LegacyBehaviors.SourcePageTableVaInTransfer</b> cap is set.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557540">DXGKARG_BUILDPAGINGBUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906830">DXGK_MEMORY_TRANSFER_DIRECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906843">DXGK_TRANSFERVIRTUALFLAGS</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>