---
UID: NC:wdm.PINITIALIZE_DMA_TRANSFER_CONTEXT
title: PINITIALIZE_DMA_TRANSFER_CONTEXT
author: windows-driver-content
description: The InitializeDmaTransferContext routine initializes an opaque DMA transfer context that is used to track pending allocations of DMA resources.
old-location: kernel\initializedmatransfercontext.htm
old-project: kernel
ms.assetid: 5E9D08FD-1F81-462F-90AA-7C4BFFB5F864
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
req.alt-api: InitializeDmaTransferContext
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
req.irql: <= DISPATCH_LEVEL
req.typenames: *PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PINITIALIZE_DMA_TRANSFER_CONTEXT callback



## -description
The <b>InitializeDmaTransferContext</b> routine initializes an opaque DMA transfer context that is used to track pending allocations of DMA resources.



## -prototype

````
PINITIALIZE_DMA_TRANSFER_CONTEXT InitializeDmaTransferContext;

NTSTATUS InitializeDmaTransferContext(
  _In_  PDMA_ADAPTER DmaAdapter,
  _Out_ PVOID        DmaTransferContext
)
{ ... }
````


## -parameters

### -param DmaAdapter [in]

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device or system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.


### -param DmaTransferContext [out]

A pointer to a caller-allocated buffer into which <b>InitializeDmaTransferContext</b> writes the initial values for the DMA transfer context.  This context is opaque to the caller. The caller must allocate a buffer that is large enough to contain the DMA transfer context. The size, in bytes, of this context is specified by the <b>DMA_TRANSFER_CONTEXT_SIZE_V1</b> constant in the Wdm.h header file.


## -returns
<b>InitializeDmaTransferContext</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
<dl>
<dt><b>STATUS_INVALID_PARAMETERS</b></dt>
</dl>This routine failed due to invalid parameter values passed by the caller.

 


## -remarks
<b>InitializeDmaTransferContext</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

An initialized DMA transfer context must be supplied as a parameter to the <a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>, <a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>, or <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a> routine. Each of these routines writes information about the requested DMA resource allocation to the DMA transfer context. This information is opaque to the caller. To cancel a pending allocation request, the caller must supply the DMA transfer context for the request to the <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a> routine.

The DMA transfer context that is supplied to <b>AllocateAdapterChannelEx</b>, <b>GetScatterGatherListEx</b>, or <b>BuildScatterGatherListEx</b> must be unique across all adapter allocation requests.


## -see-also
<dl>
<dt>
<a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pget_scatter_gather_list_ex.md">GetScatterGatherListEx</a>
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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PINITIALIZE_DMA_TRANSFER_CONTEXT callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

