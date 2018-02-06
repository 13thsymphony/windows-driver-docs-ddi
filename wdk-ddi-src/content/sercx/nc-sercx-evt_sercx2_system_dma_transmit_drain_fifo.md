---
UID: NC:sercx.EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO
title: EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO
author: windows-driver-content
description: The EvtSerCx2SystemDmaTransmitDrainFifo event callback function is called by version 2 of the serial framework extension (SerCx2) to drain the transmit FIFO in the serial controller hardware.
old-location: serports\evtsercx2systemdmatransmitdrainfifo.htm
old-project: serports
ms.assetid: 796A6C4B-0C7E-43C5-88BC-C03DAA3869A6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2systemdmatransmitdrainfifo, EvtSerCx2SystemDmaTransmitDrainFifo callback function [Serial Ports], EvtSerCx2SystemDmaTransmitDrainFifo, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO, EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO, 2/EvtSerCx2SystemDmaTransmitDrainFifo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	2.0\Sercx.h
apiname:
-	EvtSerCx2SystemDmaTransmitDrainFifo
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---


# EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO function
The <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to drain the transmit FIFO in the serial controller hardware.

## Syntax

```
EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO EvtSercx2SystemDmaTransmitDrainFifo;

void EvtSercx2SystemDmaTransmitDrainFifo(
  SERCX2SYSTEMDMATRANSMIT SystemDmaTransmit
)
{...}
```

## Parameters

`SystemDmaTransmit`

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> method to create this object.


## Return Value

None.

## Remarks

Your serial controller driver can, as an option, implement this function. If your driver implements this function, it must also implement the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo.md">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a> and <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a> event callback functions. A driver that implements these functions registers them in the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> call that creates the system-DMA-transmit object.

SerCx2 calls the <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> function, if it is implemented, to drain the transmit FIFO in the serial controller hardware at the end of a system-DMA-transmit transaction. This function makes sure that any data bytes that remain in the FIFO are transmitted to the serially connected peripheral device. After the last byte is transmitted from the FIFO, the <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> function calls the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitdrainfifocomplete.md">SerCx2SystemDmaTransmitDrainFifoComplete</a> method to notify SerCx2.

If the serial controller driver implements an <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> function, SerCx2 does not complete a pending write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) request until the driver calls <b>SerCx2SystemDmaTransmitDrainFifoComplete</b>.

If your serial controller has a hardware FIFO (or similar buffering mechanism) to hold transmit data, your driver should implement an <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> function. Otherwise, SerCx2 cannot confirm that the transmit FIFO has drained before the pending write request is completed. Instead, SerCx2 completes this request after the last byte in the write buffer is written to the transmit FIFO. There can be no guarantee that data written to the transmit FIFO will be transmitted without a significant delay. Any data that remains in the FIFO after the write request is completed might be lost before it can be transmitted to the serially connected peripheral device. This unexpected data loss in a successfully completed write request can create reliability problems for the peripheral driver.

For more information, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transactions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1. Available starting with Windows 8.1. |
| **Target Platform** | Desktop |
| **Header** | sercx.h |
| **IRQL** | Called at IRQL <= DISPATCH_LEVEL. |

## See Also

<a href="..\sercx\nf-sercx-sercx2systemdmatransmitdrainfifocomplete.md">SerCx2SystemDmaTransmitDrainFifoComplete</a>

<a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a>

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_cancel_drain_fifo.md">EvtSerCx2SystemDmaTransmitCancelDrainFifo</a>

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_purge_fifo.md">EvtSerCx2SystemDmaTransmitPurgeFifo</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_SYSTEM_DMA_TRANSMIT_DRAIN_FIFO callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>