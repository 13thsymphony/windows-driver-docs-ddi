---
UID: NC:wdm.PALLOCATE_COMMON_BUFFER_EX
title: PALLOCATE_COMMON_BUFFER_EX
author: windows-driver-content
description: The AllocateCommonBufferEx routine allocates memory for a common buffer and maps this memory so that it can be accessed both by the processor and by a device that performs DMA operations.
old-location: kernel\allocatecommonbufferex.htm
old-project: kernel
ms.assetid: F7456BD7-689C-4534-B6F0-028A5359A2E9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KSYNCHRONIZE_ROUTINE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AllocateCommonBufferEx
req.alt-loc: Wdm.h
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
req.typenames: *PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PALLOCATE_COMMON_BUFFER_EX callback



## -description
The <b>AllocateCommonBufferEx</b> routine allocates memory for a common buffer and maps this memory so that it can be accessed both by the processor and by a device that performs DMA operations.



## -prototype

````
PVOID AllocateCommonBufferEx(
  _In_     PDMA_ADAPTER      DmaAdapter,
  _In_opt_ PPHYSICAL_ADDRESS MaximumAddress,
  _In_     ULONG             Length,
  _Out_    PPHYSICAL_ADDRESS LogicalAddress,
  _In_     BOOLEAN           CacheEnabled,
  _In_     NODE_REQUIREMENT  PreferredNode
);
````


## -parameters

### -param DmaAdapter [in]

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.


### -param MaximumAddress [in, optional]

A pointer to a variable that contains the maximum logical address for the common buffer. This parameter indicates that the buffer should be allocated from memory below this address. This parameter is optional and can be specified as NULL to indicate that there is no maximum address.


### -param Length [in]

The size, in bytes, of the common buffer that is to be allocated for the DMA operation.


### -param LogicalAddress [out]

A pointer to a variable into which this routine writes the logical address that the device can use to access the common buffer. The DMA device should use this logical address instead of the physical address that is returned by a routine such as <a href="..\ntddk\nf-ntddk-mmgetphysicaladdress.md">MmGetPhysicalAddress</a>.


### -param CacheEnabled [in]

Whether the routine must enable or disable cached memory in the common buffer that is to be allocated. If TRUE, caching is enabled. If FALSE, it is disabled. If the hardware platform does not enforce cache coherency for DMA operations, then pass FALSE. For information about this parameter on ARM or ARM 64-based processors target computers, see Remarks.


### -param PreferredNode [in]

The preferred NUMA node from which the memory is to be allocated. If N is the number of NUMA nodes in a multiprocessor system, <i>PreferredNode</i> is a number in the range 0 to N–1. For a one-processor system or a non-NUMA multiprocessor system, set <i>PreferredNode</i> to zero.


## -returns
<b>AllocateCommonBufferEx</b> returns the virtual address of the memory allocated for the common buffer. If the buffer  cannot be allocated, NULL is returned.


## -remarks
<b>AllocateCommonBufferEx</b>
           is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the Version member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>AllocateCommonBufferEx</b> is an extended version of the <a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a> routine. The following list summarizes the features that are available only in the extended version:

On computers with ARM or ARM 64-based processors, cache settings in the system ACPI have a higher precedence than the <i>CacheEnabled</i> parameter value passed by the driver. If the <b>ACPI _CCA</b>  method indicates that the device is not cache coherent, the operating system disables caching even if the driver allocates cached memory with <i>CacheEnabled</i> set to TRUE.

On computers with ARM or ARM 64-based processors, the operating system allocates an uncached common buffer as Device Memory. For more information about the buffer, see sections A3.5.1, and A3.5.6 from the <a href="https://go.microsoft.com/fwlink/p/?linkid=853904">ARMv7 Architecture Reference Manual</a>.  

The processor does not permit misaligned access to Device Memory. Your driver must always access data from the common buffer by using naturally-aligned operations. Most kernel routines do not accept Device Memory as input parameters. For example, a network driver cannot pass Device Memory into <a href="..\ndis\nf-ndis-ndismindicatereceivenetbufferlists.md">NdisMIndicateReceiveNetBufferLists</a>. If your driver needs to pass data from a DMA common buffer to a kernel routine, either allocate the buffer with <i>CacheEnabled</i> set to TRUE or copy the data from the uncached common buffer into a temporary pool allocation.

For more information about DMA operations that use a common buffer, see the following topics:


## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_dma_adapter_info.md">DMA_ADAPTER</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-mmgetphysicaladdress.md">MmGetPhysicalAddress</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PALLOCATE_COMMON_BUFFER_EX callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

