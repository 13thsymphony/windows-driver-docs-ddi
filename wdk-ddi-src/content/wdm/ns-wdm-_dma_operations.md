---
UID: NS:wdm._DMA_OPERATIONS
title: "_DMA_OPERATIONS"
author: windows-driver-content
description: The DMA_OPERATIONS structure provides a table of pointers to functions that control the operation of a DMA controller.
old-location: kernel\dma_operations.htm
old-project: kernel
ms.assetid: b4a5d830-252b-410e-be2c-390371af971c
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PDMA_OPERATIONS, DMA_OPERATIONS, DMA_OPERATIONS structure [Kernel-Mode Driver Architecture], PDMA_OPERATIONS, PDMA_OPERATIONS structure pointer [Kernel-Mode Driver Architecture], _DMA_OPERATIONS, kernel.dma_operations, kstruct_a_ace4fb72-3208-4f4a-9c36-5a1f5791451a.xml, wdm/DMA_OPERATIONS, wdm/PDMA_OPERATIONS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 2000.
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	DMA_OPERATIONS
product:
- Windows
targetos: Windows
req.typenames: "*PDMA_OPERATIONS, DMA_OPERATIONS"
req.product: Windows 10 or later.
---

# _DMA_OPERATIONS structure
The <b>DMA_OPERATIONS</b> structure provides a table of pointers to functions that control the operation of a DMA controller.

## Syntax
```
typedef struct _DMA_OPERATIONS {
  ULONG                               Size;
  PPUT_DMA_ADAPTER                    PutDmaAdapter;
  PALLOCATE_COMMON_BUFFER             AllocateCommonBuffer;
  PFREE_COMMON_BUFFER                 FreeCommonBuffer;
  PALLOCATE_ADAPTER_CHANNEL           AllocateAdapterChannel;
  PFLUSH_ADAPTER_BUFFERS              FlushAdapterBuffers;
  PFREE_ADAPTER_CHANNEL               FreeAdapterChannel;
  PFREE_MAP_REGISTERS                 FreeMapRegisters;
  PMAP_TRANSFER                       MapTransfer;
  PGET_DMA_ALIGNMENT                  GetDmaAlignment;
  PREAD_DMA_COUNTER                   ReadDmaCounter;
  PGET_SCATTER_GATHER_LIST            GetScatterGatherList;
  PPUT_SCATTER_GATHER_LIST            PutScatterGatherList;
  PCALCULATE_SCATTER_GATHER_LIST_SIZE CalculateScatterGatherList;
  PBUILD_SCATTER_GATHER_LIST          BuildScatterGatherList;
  PBUILD_MDL_FROM_SCATTER_GATHER_LIST BuildMdlFromScatterGatherList;
  PGET_DMA_ADAPTER_INFO               GetDmaAdapterInfo;
  PGET_DMA_TRANSFER_INFO              GetDmaTransferInfo;
  PINITIALIZE_DMA_TRANSFER_CONTEXT    InitializeDmaTransferContext;
  PALLOCATE_COMMON_BUFFER_EX          AllocateCommonBufferEx;
  PALLOCATE_ADAPTER_CHANNEL_EX        AllocateAdapterChannelEx;
  PCONFIGURE_ADAPTER_CHANNEL          ConfigureAdapterChannel;
  PCANCEL_ADAPTER_CHANNEL             CancelAdapterChannel;
  PMAP_TRANSFER_EX                    MapTransferEx;
  PGET_SCATTER_GATHER_LIST_EX         GetScatterGatherListEx;
  PBUILD_SCATTER_GATHER_LIST_EX       BuildScatterGatherListEx;
  PFLUSH_ADAPTER_BUFFERS_EX           FlushAdapterBuffersEx;
  PFREE_ADAPTER_OBJECT                FreeAdapterObject;
  PCANCEL_MAPPED_TRANSFER             CancelMappedTransfer;
  PALLOCATE_DOMAIN_COMMON_BUFFER      AllocateDomainCommonBuffer;
  PFLUSH_DMA_BUFFER                   FlushDmaBuffer;
  PJOIN_DMA_DOMAIN                    JoinDmaDomain;
  PLEAVE_DMA_DOMAIN                   LeaveDmaDomain;
  PGET_DMA_DOMAIN                     GetDmaDomain;
} *PDMA_OPERATIONS, DMA_OPERATIONS;
```

## Members


`Size`

The size, in bytes, of this <b>DMA_OPERATIONS</b> structure.

`PutDmaAdapter`

A pointer to a system-defined routine to free a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559965">PutDmaAdapter</a>.

`AllocateCommonBuffer`

A pointer to a system-defined routine to allocate a physically contiguous DMA buffer. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540575">AllocateCommonBuffer</a>.

`FreeCommonBuffer`

A pointer to a system-defined routine to free a physically contiguous DMA buffer previously allocated by <b>AllocateCommonBuffer</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546511">FreeCommonBuffer</a>.

`AllocateAdapterChannel`

A pointer to a system-defined routine to allocate a channel for DMA operations. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>.

`FlushAdapterBuffers`

A pointer to a system-defined routine to flush data from the system or bus-master adapter's internal cache after a DMA operation. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>.

`FreeAdapterChannel`

A pointer to a system-defined routine to free a channel previously allocated for DMA operations by <b>AllocateAdapterChannel</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546507">FreeAdapterChannel</a>.

`FreeMapRegisters`

A pointer to a system-defined routine to free map registers allocated for DMA operations. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546513">FreeMapRegisters</a>.

`MapTransfer`

A pointer to a system-defined routine to begin a DMA operation. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>.

`GetDmaAlignment`

A pointer to a system-defined routine to obtain the DMA alignment requirements of the controller. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546530">GetDmaAlignment</a>.

`ReadDmaCounter`

A pointer to a system-defined routine to obtain the current transfer count for a DMA operation. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560782">ReadDmaCounter</a>.

`GetScatterGatherList`

A pointer to a system-defined routine that allocates map registers and creates a scatter/gather list for DMA. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a>.

`PutScatterGatherList`

A pointer to a system-defined routine that frees map registers and a scatter/gather list after a DMA operation is complete. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559967">PutScatterGatherList</a>.

`CalculateScatterGatherList`

A pointer to a system-defined routine that determines the buffer size needed to hold the scatter/gather list that describes an I/O data  buffer. This member is available only in versions 2 and later of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540716">CalculateScatterGatherList</a>.

`BuildScatterGatherList`

A pointer to a system-defined routine that allocates map registers and creates a scatter/gather list for DMA in a driver-supplied buffer. This member is available only in versions 2 and later of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540689">BuildScatterGatherList</a>.

`BuildMdlFromScatterGatherList`

A pointer to a system-defined routine that builds an MDL corresponding to a scatter/gather list. This member is available only in versions 2 and later of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540686">BuildMdlFromScatterGatherList</a>.

`GetDmaAdapterInfo`

A pointer to a system-defined routine that describes the capabilities of a bus-master DMA device or a system DMA controller. <b>GetDmaAdapterInfo</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451121">GetDmaAdapterInfo</a>.

`GetDmaTransferInfo`

A pointer to a system-defined routine that describes the allocation requirements for a scatter/gather list. This routine replaces <a href="https://msdn.microsoft.com/library/windows/hardware/ff540716">CalculateScatterGatherList</a>. <b>GetDmaTransferInfo</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451125">GetDmaTransferInfo</a>.

`InitializeDmaTransferContext`

A pointer to a system-defined routine that initializes an opaque DMA transfer context. The operating system stores the internal status of a DMA transfer in this context. <b>InitializeDmaTransferContext</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451191">InitializeDmaTransferContext</a>.

`AllocateCommonBufferEx`

A pointer to a system-defined routine that allocates memory for a common buffer and maps this memory so that it can accessed both by the processor and by a DMA device. <b>AllocateCommonBufferEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406344">AllocateCommonBufferEx</a>.

`AllocateAdapterChannelEx`

A pointer to a system-defined routine that allocates the resources required for a DMA transfer and then calls the driver-supplied <i>AdapterControl</i> routine to initiate the DMA transfer. <b>AllocateAdapterChannelEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406340">AllocateAdapterChannelEx</a>.

`ConfigureAdapterChannel`

A pointer to a system-defined routine enables a custom function that is implemented by the DMA controller. <b>ConfigureAdapterChannel</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450939">ConfigureAdapterChannel</a>.

`CancelAdapterChannel`

A pointer to a system-defined routine that tries to cancel a pending request to allocate a DMA channel. <b>CancelAdapterChannel</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406374">CancelAdapterChannel</a>.

`MapTransferEx`

A pointer to a system-defined routine that sets up map registers to map the physical addresses in a scatter/gather list to the logical addresses that are required to do a DMA transfer. <b>MapTransferEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a>.

`GetScatterGatherListEx`

A pointer to a system-defined routine that   allocates resources required for a DMA transfer, builds a scatter/gather list, and then calls the driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff540513">AdapterListControl</a> routine to initiate the DMA transfer. <b>GetScatterGatherListEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451134">GetScatterGatherListEx</a>. This routine is a wrapper of <b>AllocateAdapterChannelEx</b> and <b>MapTransferEx</b>.

`BuildScatterGatherListEx`

A pointer to a system-defined routine that   builds a scatter/gather list in a caller-allocated buffer, and then calls the driver-supplied <i>AdapterListControl</i> routine to initiate the DMA transfer. <b>BuildScatterGatherListEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406371">BuildScatterGatherListEx</a>.

`FlushAdapterBuffersEx`

A pointer to a system-defined routine that  flushes any data that remains in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer. For a device that uses a system DMA controller, this routine cancels the current DMA transfer on the controller if the transfer is not complete. <b>FlushAdapterBuffersEx</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451102">FlushAdapterBuffersEx</a>.

`FreeAdapterObject`

A pointer to a system-defined routine that releases the specified adapter object after a driver has completed all DMA operations. <b>FreeAdapterObject</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451107">FreeAdapterObject</a>.

`CancelMappedTransfer`

A pointer to a system-defined routine that cancels a mapped transfer. <b>CancelMappedTransfer</b> is available only in version 3 of <b>DMA_OPERATIONS</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406377">CancelMappedTransfer</a>.

`AllocateDomainCommonBuffer`



`FlushDmaBuffer`



`JoinDmaDomain`



`LeaveDmaDomain`



`GetDmaDomain`



## Remarks
All members of this structure, with the exception of <b>Size</b>, are pointers to functions that drivers use to perform DMA operations for their devices. Drivers obtain these pointers by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine. The version of the <b>DMA_OPERATIONS</b> structure that this routine returns depends on the <b>Version</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543107">DEVICE_DESCRIPTION</a> structure that is passed to <b>IoGetDmaAdapter</b> as an input parameter. If <b>Version</b> is DEVICE_DESCRIPTION_VERSION or DEVICE_DESCRIPTION_VERSION1, version 1 of this structure is returned. If <b>Version</b> is DEVICE_DESCRIPTION_VERSION2, version 2 of this structure is returned. Version 2 of <b>DMA_OPERATIONS</b> is available starting with  Windows XP. If <b>Version</b> is DEVICE_DESCRIPTION_VERSION3, version 3 of this structure is returned. Version 3 of <b>DMA_OPERATIONS</b> is available starting with  Windows 8.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 2000. Supported starting with  Windows 2000. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406340">AllocateAdapterChannelEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540575">AllocateCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406344">AllocateCommonBufferEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540686">BuildMdlFromScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540689">BuildScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406371">BuildScatterGatherListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540716">CalculateScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406374">CancelAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406377">CancelMappedTransfer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450939">ConfigureAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543107">DEVICE_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545917">FlushAdapterBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451102">FlushAdapterBuffersEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546507">FreeAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451107">FreeAdapterObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546511">FreeCommonBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546513">FreeMapRegisters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451121">GetDmaAdapterInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546530">GetDmaAlignment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451125">GetDmaTransferInfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546531">GetScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451134">GetScatterGatherListEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451191">InitializeDmaTransferContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406521">MapTransferEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559965">PutDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559967">PutScatterGatherList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560782">ReadDmaCounter</a>