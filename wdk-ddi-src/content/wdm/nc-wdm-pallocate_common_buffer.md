---
UID: NC:wdm.PALLOCATE_COMMON_BUFFER
title: PALLOCATE_COMMON_BUFFER
author: windows-driver-content
description: The AllocateCommonBuffer routine allocates memory and maps it so that it is simultaneously accessible from both the processor and a device for DMA operations.
old-location: kernel\allocatecommonbuffer.htm
old-project: kernel
ms.assetid: 4edaae35-8ac4-4a7a-949b-8a86b45ff391
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: AllocateCommonBuffer, AllocateCommonBuffer callback function [Kernel-Mode Driver Architecture], PALLOCATE_COMMON_BUFFER, kdma_0e4a27db-db3e-48db-81c2-d83a342a0cbc.xml, kernel.allocatecommonbuffer, wdm/AllocateCommonBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlDispatch
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
-	Wdm.h
api_name:
-	AllocateCommonBuffer
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# PALLOCATE_COMMON_BUFFER callback function
The <b>AllocateCommonBuffer</b> routine allocates memory and maps it so that it is simultaneously accessible from both the processor and a device for DMA operations.

## Syntax

```
PALLOCATE_COMMON_BUFFER PallocateCommonBuffer;

PVOID PallocateCommonBuffer(
  PDMA_ADAPTER DmaAdapter,
  ULONG Length,
  PPHYSICAL_ADDRESS LogicalAddress,
  BOOLEAN CacheEnabled
)
{...}
```

## Parameters

`DmaAdapter`

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

`Length`

Specifies the number of bytes of memory to allocate.

`LogicalAddress`

Pointer to a variable that receives the logical address the device can use to access the allocated buffer. Use this address rather than calling <a href="..\ntddk\nf-ntddk-mmgetphysicaladdress.md">MmGetPhysicalAddress</a> because the system can take into account any platform-specific memory restrictions.

`CacheEnabled`

Specifies whether the allocated memory can be cached.

This parameter is ignored. The operating system determines whether to enable cached memory in the common buffer that is to be allocated. That decision is based on the processor architecture and device bus. 

On computers with x86-based, x64-based, and Itanium-based processors, cached memory is enabled. It is assumed that all DMA operations performed by a device are coherent with the relevant CPU caches, which might be caching that memory. If your driver needs to disable caching, call <a href="..\wdm\nc-wdm-pallocate_common_buffer_ex.md">AllocateCommonBufferEx</a> instead.

On computers with ARM or ARM 64-based processors, the operating system does not automatically enable cached memory for all devices. The system relies on the <b>ACPI_CCA</b> method for each device to determine whether the device is cache-coherent.


## Return Value

<b>AllocateCommonBuffer</b> returns the base virtual address of the allocated range. If the buffer cannot be allocated, it returns <b>NULL</b>.

## Remarks

<b>AllocateCommonBuffer</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <b>DMA_OPERATIONS</b>
           structure. Drivers obtain the address of this routine by calling <a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>.

<b>AllocateCommonBuffer</b> supports DMA in which the device and the processor continuously communicate through system memory, as in a control structure for a bus-master DMA device.

<b>AllocateCommonBuffer</b> also supports subordinate devices whose drivers use a system DMA controller's autoinitialize mode.

<b>AllocateCommonBuffer</b> does the following:

<ul>
<li>
Allocates memory that can be reached from both the processor and the device. This memory appears contiguous to the device.

</li>
<li>
Allocates map registers to map the buffer, if required by the system.

</li>
<li>
Sets up a translation for the device, including loading map registers if necessary.

</li>
</ul>
To use resident system memory economically, drivers should allocate as few of these buffers per device as possible. <b>AllocateCommonBuffer</b> allocates at least a page of memory, regardless of the requested <i>Length</i>. After a successful allocation requesting fewer than PAGE_SIZE bytes, the caller can access only the requested <i>Length</i>. After a successful allocation requesting more than an integral multiple of PAGE_SIZE bytes, any remaining bytes on the last allocated page are inaccessible to the caller.

If a driver needs several pages of common buffer space, but the pages need not be contiguous, the driver should make several one-page requests to <b>AllocateCommonBuffer</b> instead of one large request. This approach conserves contiguous memory.

Drivers typically call <b>AllocateCommonBuffer</b> as part of device start-up, during their response to a PnP <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request. After startup, it is possible that only one-page requests will succeed, if any.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlDispatch |

## See Also

<a href="..\wdm\nc-wdm-pfree_common_buffer.md">FreeCommonBuffer</a>



<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>



<a href="..\wdm\nf-wdm-iogetdmaadapter.md">IoGetDmaAdapter</a>



<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PALLOCATE_COMMON_BUFFER callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>