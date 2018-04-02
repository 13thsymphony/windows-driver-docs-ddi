---
UID: NF:sercx.SerCx2SystemDmaTransmitDrainFifoComplete
title: SerCx2SystemDmaTransmitDrainFifoComplete function
author: windows-driver-content
description: The SerCx2SystemDmaTransmitDrainFifoComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished draining the data from the transmit FIFO in the serial controller hardware.
old-location: serports\sercx2systemdmatransmitdrainfifocomplete.htm
old-project: serports
ms.assetid: 324EB2B8-9CF0-4A8B-B6D0-B5748EBCB53E
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SerCx2SystemDmaTransmitDrainFifoComplete, SerCx2SystemDmaTransmitDrainFifoComplete, SerCx2SystemDmaTransmitDrainFifoComplete method [Serial Ports], serports.sercx2systemdmatransmitdrainfifocomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Universal
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	2.0\Sercx.h
api_name:
-	SerCx2SystemDmaTransmitDrainFifoComplete
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---


# SerCx2SystemDmaTransmitDrainFifoComplete function
The <b>SerCx2SystemDmaTransmitDrainFifoComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished draining the data from the transmit FIFO in the serial controller hardware.

## Syntax

```
void SerCx2SystemDmaTransmitDrainFifoComplete(
  SERCX2SYSTEMDMATRANSMIT SystemDmaTransmit
);
```

## Parameters

`SystemDmaTransmit`

TBD


## Return Value

None.

## Remarks

SerCx2 calls the <a href="https://msdn.microsoft.com/796A6C4B-0C7E-43C5-88BC-C03DAA3869A6">EvtSerCx2SystemDmaTransmitDrainFifo</a> event callback function, if it is implemented, to drain the transmit FIFO at the end of a system-DMA-transmit transaction. This function makes sure that any data bytes that remain in the FIFO are transmitted from the serial port before SerCx2 completes the write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) request that initiated the transaction. After the last byte is transmitted from the FIFO, the serial controller driver must call the <b>SerCx2SystemDmaTransmitDrainFifoComplete</b> method to notify SerCx2. SerCx2 expects this notification and does not complete the write request until it is notified.

The serial controller must call <b>SerCx2SystemDmaTransmitDrainFifoComplete</b> only in response to a call to the <i>EvtSerCx2SystemDmaTransmitDrainFifo</i> function.

For more information, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transactions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1.  |
| **Target Platform** | Universal |
| **Header** | sercx.h |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/796A6C4B-0C7E-43C5-88BC-C03DAA3869A6">EvtSerCx2SystemDmaTransmitDrainFifo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265288">SerCx2SystemDmaTransmitCreate</a>