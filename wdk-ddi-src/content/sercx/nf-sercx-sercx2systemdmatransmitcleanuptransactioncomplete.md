---
UID: NF:sercx.SerCx2SystemDmaTransmitCleanupTransactionComplete
title: SerCx2SystemDmaTransmitCleanupTransactionComplete function
author: windows-driver-content
description: The SerCx2SystemDmaTransmitCleanupTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a system-DMA-transmit transaction.
old-location: serports\sercx2systemdmatransmitcleanuptransactioncomplete.htm
old-project: serports
ms.assetid: 9B2899AB-055B-458B-A9C5-958B8B2E809D
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SerCx2SystemDmaTransmitCleanupTransactionComplete, SerCx2SystemDmaTransmitCleanupTransactionComplete, SerCx2SystemDmaTransmitCleanupTransactionComplete method [Serial Ports], serports.sercx2systemdmatransmitcleanuptransactioncomplete
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
-	SerCx2SystemDmaTransmitCleanupTransactionComplete
product:
- Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---


# SerCx2SystemDmaTransmitCleanupTransactionComplete function
The <b>SerCx2SystemDmaTransmitCleanupTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished cleaning up the serial controller's hardware state after a system-DMA-transmit transaction.

## Syntax

```
void SerCx2SystemDmaTransmitCleanupTransactionComplete(
  SERCX2SYSTEMDMATRANSMIT SystemDmaTransmit
);
```

## Parameters

`SystemDmaTransmit`

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265288">SerCx2SystemDmaTransmitCreate</a> method to create this object.


## Return Value

None.

## Remarks

After a system-DMA-transmit transaction ends, SerCx2 calls the <a href="https://msdn.microsoft.com/DAC33D61-F85C-43A7-9F4D-AA31F8CA4430">EvtSerCx2SystemDmaTransmitCleanupTransaction</a> event callback function, if it is implemented, to clean up the serial controller state. In response to this call, the driver should do any clean-up work that is needed; then the driver must call <b>SerCx2SystemDmaTransmitCleanupTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the next transaction until it is notified.

The serial controller driver must call <b>SerCx2SystemDmaTransmitCleanupTransactionComplete</b> only in response to a call to the <i>EvtSerCx2SystemDmaTransmitCleanupTransaction</i> function.

For more information, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transaction</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1.  |
| **Target Platform** | Universal |
| **Header** | sercx.h |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/DAC33D61-F85C-43A7-9F4D-AA31F8CA4430">EvtSerCx2SystemDmaTransmitCleanupTransaction</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMATRANSMIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265288">SerCx2SystemDmaTransmitCreate</a>