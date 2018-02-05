---
UID : NC:wdm.PFREE_ADAPTER_CHANNEL
title : PFREE_ADAPTER_CHANNEL
author : windows-driver-content
description : The FreeAdapterChannel routine releases the system DMA controller when a driver has completed all DMA operations necessary to satisfy the current IRP.
old-location : kernel\freeadapterchannel.htm
old-project : kernel
ms.assetid : 916531dd-4768-436a-910c-07d49924ac48
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.freeadapterchannel, FreeAdapterChannel, FreeAdapterChannel callback function [Kernel-Mode Driver Architecture], FreeAdapterChannel, PFREE_ADAPTER_CHANNEL, PFREE_ADAPTER_CHANNEL, wdm/FreeAdapterChannel, kdma_f48025a6-96a2-4bdd-8b48-6c939bdf738b.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : IrqlDispatch, IrqlDispatch(storport)
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product : Windows 10 or later.
---


# PFREE_ADAPTER_CHANNEL callback function
The <b>FreeAdapterChannel</b> routine releases the system DMA controller when a driver has completed all DMA operations necessary to satisfy the current IRP.

## Syntax

```
PFREE_ADAPTER_CHANNEL PfreeAdapterChannel;

void PfreeAdapterChannel(
  PDMA_ADAPTER DmaAdapter
)
{...}
```

## Parameters

`DmaAdapter`

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>  structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.


## Return Value

None

## Remarks

<b>FreeAdapterChannel</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

After a driver has transferred all the data and called <a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>, it calls <b>FreeAdapterChannel</b> to release the system DMA controller that was previously allocated with a call to <b>AllocateAdapterChannel</b>.

<b>FreeAdapterChannel</b> frees any map registers that were allocated by an earlier call to <b>AllocateAdapterChannel</b>. A driver calls this routine only if its <a href="..\wdm\nc-wdm-driver_control.md">AdapterControl</a> routine returns <b>KeepObject</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** | IrqlDispatch, IrqlDispatch(storport) |

## See Also

<a href="..\wdm\nc-wdm-pfree_map_registers.md">FreeMapRegisters</a>

<a href="..\wdm\nc-wdm-pmap_transfer.md">MapTransfer</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>

<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>

<a href="..\wdm\nc-wdm-pallocate_adapter_channel.md">AllocateAdapterChannel</a>

<a href="..\wdm\nc-wdm-pflush_adapter_buffers.md">FlushAdapterBuffers</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PFREE_ADAPTER_CHANNEL callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>