---
UID: NC:wdm.PFLUSH_ADAPTER_BUFFERS
title: PFLUSH_ADAPTER_BUFFERS
author: windows-driver-content
description: The FlushAdapterBuffers routine flushes any data remaining in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer operation.
old-location: kernel\flushadapterbuffers.htm
old-project: kernel
ms.assetid: cd6cf9af-c600-465c-b8f3-ca0f972780a5
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: FlushAdapterBuffers, FlushAdapterBuffers callback function [Kernel-Mode Driver Architecture], PFLUSH_ADAPTER_BUFFERS, kdma_97ac2c04-7f7e-495d-b846-d4f0ea27bdac.xml, kernel.flushadapterbuffers, wdm/FlushAdapterBuffers
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdm.h
api_name:
-	FlushAdapterBuffers
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# PFLUSH_ADAPTER_BUFFERS callback function
The <b>FlushAdapterBuffers</b> routine flushes any data remaining in the system DMA controller's internal cache or in a bus-master adapter's internal cache at the end of a DMA transfer operation.

## Syntax

```
PFLUSH_ADAPTER_BUFFERS PflushAdapterBuffers;

BOOLEAN PflushAdapterBuffers(
  PDMA_ADAPTER DmaAdapter,
  PMDL Mdl,
  PVOID MapRegisterBase,
  PVOID CurrentVa,
  ULONG Length,
  BOOLEAN WriteToDevice
)
{...}
```

## Parameters

`DmaAdapter`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a> structure returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> that represents the bus-master adapter or DMA controller.

`Mdl`

Pointer to the MDL that describes the buffer previously passed in the driver's call to <b>MapTransfer</b>.

`MapRegisterBase`

Specifies the map registers allocated for the DMA operation.  The system passes this value  to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540504">AdapterControl</a> routine.

`CurrentVa`

Pointer to the current virtual address in the buffer, described by the <i>Mdl</i>, where the I/O operation occurred. This value must be the same as the initial <i>CurrentVa</i> value passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>.

`Length`

Specifies the length, in bytes, of the buffer.

`WriteToDevice`

Specifies the direction of the DMA transfer operation: <b>TRUE</b> for a transfer from a buffer in system memory to the driver's device.


## Return Value

<b>FlushAdapterBuffers</b> returns <b>TRUE</b> if any data remaining in the DMA controller's or bus-master adapter's internal cache has been successfully flushed into system memory or out to the device.

## Remarks

<b>FlushAdapterBuffers</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

To ensure that a DMA transfer is complete, every driver that performs DMA operations must call <b>FlushAdapterBuffers</b> before completing the IRP that requested the DMA transfer and before freeing the map registers.

A driver can get the initial <i>CurrentVa</i> for the start of a packet-based DMA transfer by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>. However, the value returned is an index into the <i>Mdl</i>, rather than a valid virtual address. If the driver must split a large transfer request into more than one DMA operation, it must update <i>CurrentVa</i> and <i>Length</i> for each DMA operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | IrqlDispatch |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540573">AllocateAdapterChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544062">DMA_ADAPTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544071">DMA_OPERATIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552041">KeFlushIoBuffers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554402">MapTransfer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554539">MmGetMdlVirtualAddress</a>