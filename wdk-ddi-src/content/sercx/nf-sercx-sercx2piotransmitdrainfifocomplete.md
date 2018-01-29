---
UID : NF:sercx.SerCx2PioTransmitDrainFifoComplete
title : SerCx2PioTransmitDrainFifoComplete function
author : windows-driver-content
description : The SerCx2PioTransmitDrainFifoComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished draining the data from the transmit FIFO in the serial controller hardware.
old-location : serports\sercx2piotransmitdrainfifocomplete.htm
old-project : serports
ms.assetid : A1AF3D23-D0F4-44C0-A1B1-E7775FCA3699
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : serports.sercx2piotransmitdrainfifocomplete, SerCx2PioTransmitDrainFifoComplete, SerCx2PioTransmitDrainFifoComplete method [Serial Ports], 2/SerCx2PioTransmitDrainFifoComplete
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : sercx.h
req.include-header : 
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 8.1.
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SERCX_STATUS, *PSERCX_STATUS
req.product : Windows 10 or later.
---


# SerCx2PioTransmitDrainFifoComplete function
The <b>SerCx2PioTransmitDrainFifoComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished draining the data from the transmit FIFO in the serial controller hardware.

## Syntax

````
VOID SerCx2PioTransmitDrainFifoComplete(
  [in] SERCX2PIOTRANSMIT PioTransmit
);
````

## Parameters

`PioTransmit`

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method to create this object.


## Return Value

None.

## Remarks

SerCx2 calls the <b>SerCx2PioTransmitDrainFifoComplete</b> event callback function, if it is implemented, to drain the transmit FIFO at the end of a PIO-transmit transaction. This function makes sure that any data bytes that remain in the FIFO are transmitted from the serial port before SerCx2 completes the write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) request that initiated the transaction. After the last byte is transmitted from the FIFO, the serial controller driver must call the <b>SerCx2PioTransmitDrainFifoComplete</b> method to notify SerCx2. SerCx2 expects this notification and does not complete the write request until it is notified.

The serial controller driver must call <b>SerCx2PioTransmitDrainFifoComplete</b> only in response to a call to the <i>EvtSerCx2PioTransmitDrainFifo</i> function.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sercx.h |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>

<a href="..\sercx\nc-sercx-evt_sercx2_pio_transmit_drain_fifo.md">EvtSerCx2PioTransmitDrainFifo</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2PioTransmitDrainFifoComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>