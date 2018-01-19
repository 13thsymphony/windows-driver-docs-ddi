---
UID : NC:wdm.PBUILD_SCATTER_GATHER_LIST
title : PBUILD_SCATTER_GATHER_LIST
author : windows-driver-content
description : The BuildScatterGatherList routine prepares the system for a DMA operation, using a driver-supplied buffer to build the scatter/gather list.
old-location : kernel\buildscattergatherlist.htm
old-project : kernel
ms.assetid : 678b568a-2efe-443e-89f5-84d012431755
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows XP and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : BuildScatterGatherList
req.alt-loc : wdm.h
req.ddi-compliance : IrqlDispatch
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : DISPATCH_LEVEL
req.typenames : WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product : Windows 10 or later.
---


# PBUILD_SCATTER_GATHER_LIST callback function
The <b>BuildScatterGatherList</b> routine prepares the system for a DMA operation, using a driver-supplied buffer to build the scatter/gather list.

## Syntax

```
PBUILD_SCATTER_GATHER_LIST PbuildScatterGatherList;

NTSTATUS PbuildScatterGatherList(
  PDMA_ADAPTER DmaAdapter,
  PDEVICE_OBJECT DeviceObject,
  PMDL Mdl,
  PVOID CurrentVa,
  ULONG Length,
  PDRIVER_LIST_CONTROL ExecutionRoutine,
  PVOID Context,
  BOOLEAN WriteToDevice,
  PVOID ScatterGatherBuffer,
  ULONG ScatterGatherLength
)
{...}
```

## Parameters

`DmaAdapter`

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

`DeviceObject`

Pointer to the device object that represents the target device for the DMA operation.

`Mdl`

Pointer to the MDL that describes the buffer specified by the <b>MdlAddress</b> member of the current IRP.

`CurrentVa`

Pointer to the current virtual address in the MDL for the buffer to be mapped for a DMA transfer operation.

`Length`

Specifies the length, in bytes, of the buffer to be mapped.

`ExecutionRoutine`

Pointer to a driver-supplied <a href="..\wdm\nc-wdm-driver_list_control.md">AdapterListControl</a> routine, which is called at IRQL = DISPATCH_LEVEL when the system DMA controller or bus-master adapter is available.

`Context`

Pointer to the driver-determined context passed to <i>ExecutionRoutine</i> when it is called.

`WriteToDevice`

Indicates the direction of the DMA transfer: <b>TRUE</b> for a transfer from the buffer to the device, and <b>FALSE</b> otherwise.

`ScatterGatherBuffer`

Pointer to the caller-supplied buffer that the routine fills with a <a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a> structure.

`ScatterGatherLength`




## Return Value

<b>BuildScatterGatherList</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation is completed successfully.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The system has insufficient map registers available for the transfer.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The specified <i>Length</i> is too big to fit within the buffer.

## Remarks

<b>BuildScatterGatherList</b>
           is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION2. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>BuildScatterGatherList</b> performs the same operation as <a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>, except that it uses the buffer supplied in the <i>ScatterGatherBuffer</i> parameter to hold the scatter/gather list that it creates. In contrast, <b>GetScatterGatherList</b> dynamically allocates a buffer to hold the scatter/gather list. If insufficient memory is available to allocate the buffer, <b>GetScatterGatherList</b> can fail with a STATUS_INSUFFICIENT_RESOURCES error. Drivers that must avoid this scenario can preallocate a buffer to hold the scatter/gather list, and use <b>BuildScatterGatherList</b> instead.

A driver can use the <a href="..\wdm\nc-wdm-pcalculate_scatter_gather_list_size.md">CalculateScatterGatherList</a> routine to determine the size of buffer to allocate to hold the scatter/gather list.

The driver should retain the pointer to the scatter/gather list in <i>ScatterGatherBuffer</i> for use when the driver calls <a href="..\wdm\nc-wdm-pput_scatter_gather_list.md">PutScatterGatherList</a>. The driver must call <b>PutScatterGatherList</b> (which flushes the list) before it can access the data in the list.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | IrqlDispatch |

## See Also

<dl>
<dt>
<a href="..\wdm\nc-wdm-pbuild_mdl_from_scatter_gather_list.md">BuildMdlFromScatterGatherList</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pcalculate_scatter_gather_list_size.md">CalculateScatterGatherList</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pget_scatter_gather_list.md">GetScatterGatherList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pput_scatter_gather_list.md">PutScatterGatherList</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_scatter_gather_list.md">SCATTER_GATHER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PBUILD_SCATTER_GATHER_LIST callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>