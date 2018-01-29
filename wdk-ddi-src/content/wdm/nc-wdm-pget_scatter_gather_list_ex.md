---
UID : NC:wdm.PGET_SCATTER_GATHER_LIST_EX
title : PGET_SCATTER_GATHER_LIST_EX
author : windows-driver-content
description : The GetScatterGatherListEx routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied AdapterListControl routine to initiate the DMA transfer.
old-location : kernel\getscattergatherlistex.htm
old-project : kernel
ms.assetid : BDEC9AFC-2BA1-4E2C-83B4-F21B220B8B3B
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.getscattergatherlistex, GetScatterGatherListEx, GetScatterGatherListEx callback function [Kernel-Mode Driver Architecture], GetScatterGatherListEx, PGET_SCATTER_GATHER_LIST_EX, PGET_SCATTER_GATHER_LIST_EX, wdm/GetScatterGatherListEx, DMA_SYNCHRONOUS_CALLBACK
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product : Windows 10 or later.
---


# PGET_SCATTER_GATHER_LIST_EX callback function
The <b>GetScatterGatherListEx</b> routine allocates the resources that are required for a DMA transfer, builds a scatter/gather list, and calls the driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine to initiate the DMA transfer.
<div class="alert"><b>Note</b>  Do not call this routine for a system DMA device.</div><div> </div>

## Syntax

```
PGET_SCATTER_GATHER_LIST_EX PgetScatterGatherListEx;

NTSTATUS PgetScatterGatherListEx(
  PDMA_ADAPTER DmaAdapter,
  PDEVICE_OBJECT DeviceObject,
  PVOID DmaTransferContext,
  PMDL Mdl,
  ULONGLONG Offset,
  ULONG Length,
  ULONG Flags,
  PDRIVER_LIST_CONTROL ExecutionRoutine,
  PVOID Context,
  BOOLEAN WriteToDevice,
  PDMA_COMPLETION_ROUTINE DmaCompletionRoutine,
  PVOID CompletionContext,
  PSCATTER_GATHER_LIST *ScatterGatherList
)
{...}
```

## Parameters

`DmaAdapter`

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's bus-master DMA device. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.

`DeviceObject`

A pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. This structure is the physical device object (PDO) that represents the target device for the requested DMA operation.

`DmaTransferContext`

A pointer to an initialized DMA transfer context. This context was initialized by a previous call to the <a href="..\wdm\nc-wdm-pinitialize_dma_transfer_context.md">InitializeDmaTransferContext</a> routine. This context must be unique across all adapter allocation requests. To cancel a pending allocation request, the caller must supply the DMA transfer context for the request to the <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a> routine.

`Mdl`

A pointer to an MDL chain that describes the physical page layout for a collection of locked-down buffers in virtual memory. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters. For more information about MDL chains, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.

`Offset`

The starting offset for the scatter/gather DMA transfer. This parameter is a byte offset from the start of the buffer in the first MDL in the MDL chain. If the MDLs in the MDL chain specify a total of N bytes of buffer space, valid values of <i>Offset</i> are in the range 0 to N–1.

`Length`

The length, in bytes, of the DMA transfer. If the MDL chain specifies a total of N bytes of buffer space, valid values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.

`Flags`

The adapter channel allocation flags. The following flag is supported.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DMA_SYNCHRONOUS_CALLBACK"></a><a id="dma_synchronous_callback"></a><dl>
<dt><b>DMA_SYNCHRONOUS_CALLBACK</b></dt>
</dl>
</td>
<td width="60%">
The <b>GetScatterGatherListEx</b> routine is called synchronously. If this flag is set, and the required DMA resources are not immediately available, the call fails and returns STATUS_INSUFFICIENT_RESOURCES.

</td>
</tr>
</table> 

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> parameter is optional and can be NULL. If this flag is not set, <i>ExecutionRoutine</i> must be a valid, non-<b>NULL</b> pointer. For more information about this flag, see the Remarks section.

`ExecutionRoutine`

A pointer to the driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine that initiates the DMA transfer for the driver. The I/O manager calls the <i>AdapterListControl</i> routine after the required resources are allocated for the adapter object. After the <i>AdapterListControl</i> routine returns, the I/O manager automatically frees the adapter object and the resources that were allocated for this object.

If the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set, the <i>ExecutionRoutine</i> parameter is optional and can be NULL. If this parameter is NULL, the caller can use the resources allocated by <b>GetScatterGatherListEx</b> to perform the DMA transfer after <b>GetScatterGatherListEx</b> returns. For more information, see the Remarks section.

`Context`

The driver-determined, adapter-control context. This context is passed to the <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine as the <i>Context</i> parameter.

`WriteToDevice`

The direction of the DMA transfer. Set this parameter to TRUE for a write operation, which transfers data from memory to the device. Set this parameter to FALSE for a read operation, which transfers data from the device to memory.

`DmaCompletionRoutine`

Not used. Set to <b>NULL</b>.

`CompletionContext`

Not used. Set to <b>NULL</b>.

`*ScatterGatherList`




## Return Value

<b>GetScatterGatherListEx</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETERS</b></dt>
</dl>
</td>
<td width="60%">
The routine failed due to invalid parameter values passed by the caller.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine failed to allocate resources required for the DMA transfer.

</td>
</tr>
</table>

## Remarks

<b>GetScatterGatherListEx</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

Use <b>GetScatterGatherListEx</b> only for bus-master adapters. Do not use this routine for a system DMA adapter.

The driver of a bus-master device can use
     <b>GetScatterGatherListEx</b> to combine the operations performed by the <a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a> and <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a> routines into a one call. <b>GetScatterGatherListEx</b> performs the following operations:
<ol>
<li>Allocates the resources that are required for the DMA transfer.</li>
<li>Builds a scatter/gather list based on the values of the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.</li>
<li>Calls the driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine and supplies the scatter/gather list to this routine as a parameter.</li>
</ol>The allocated resources are automatically released after the <i>AdapterListControl</i> routine returns.  If <b>GetScatterGatherListEx</b> is called synchronously (that is, if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set), the <i>AdapterListControl</i> routine can be omitted.  In this case, the caller uses the allocated resources to initiate the DMA transfer after <b>GetScatterGatherListEx</b> returns. The caller must explicitly release these resources.

By default, <b>GetScatterGatherListEx</b> returns asynchronously, without waiting for the requested resource allocation to complete. After this return, the caller can, if necessary, cancel the pending allocation request by calling the <a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a> routine.

If the calling driver sets the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag, the <b>GetScatterGatherListEx</b> routine behaves as follows:
<ul>
<li>
If the requested resources are not immediately available, <b>GetScatterGatherListEx</b> does not wait for resources, does not build a scatter/gather list, and does not call the <i>AdapterListControl</i> routine. Instead,  <b>GetScatterGatherListEx</b> fails and returns STATUS_INSUFFICIENT_RESOURCES.

</li>
<li>
The driver is not required to supply an <i>AdapterListControl</i> routine if the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag is set.

</li>
<li>
If the driver supplies an <i>AdapterListControl</i> routine, the <b>DMA_SYNCHRONOUS_CALLBACK</b> flag indicates that this routine is to be called in the context of the calling thread, before <b>GetScatterGatherListEx</b> returns.

</li>
<li>
If the driver does not supply an <i>AdapterListControl</i> routine, the driver can use the allocated resources and scatter/gather list after <b>GetScatterGatherListEx</b> returns. In this case, the driver must supply a valid, non-NULL <i>ScatterGatherList</i> pointer. In addition, after the driver initiates the DMA transfer, the driver must call the <a href="..\wdm\nc-wdm-pfree_adapter_object.md">FreeAdapterObject</a> routine to free the resources that <b>GetScatterGatherListEx</b> allocated for the adapter object.

</li>
</ul><b>GetScatterGatherListEx</b> is an extended version of the <a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a> routine. The following features are available only in the extended version:



<b>GetScatterGatherListEx</b> is similar to the <a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a> routine, except that <b>GetScatterGatherListEx</b> automatically allocates the buffer for the scatter/gather list.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>

<a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450991">DmaCompletionRoutine</a>

<a href="..\wdm\nc-wdm-driver_control.md">AdapterListControl</a>

<a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>

<a href="..\wdm\nc-wdm-pbuild_scatter_gather_list_ex.md">BuildScatterGatherListEx</a>

<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="..\wdm\nc-wdm-pinitialize_dma_transfer_context.md">InitializeDmaTransferContext</a>

<a href="..\wdm\nc-wdm-pallocate_adapter_channel_ex.md">AllocateAdapterChannelEx</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546507">FreeAdapterChannel</a>

<a href="..\wdm\nc-wdm-pcancel_adapter_channel.md">CancelAdapterChannel</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PGET_SCATTER_GATHER_LIST_EX callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>