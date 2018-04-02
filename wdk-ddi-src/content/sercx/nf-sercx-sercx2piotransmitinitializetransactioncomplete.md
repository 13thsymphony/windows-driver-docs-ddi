---
UID: NF:sercx.SerCx2PioTransmitInitializeTransactionComplete
title: SerCx2PioTransmitInitializeTransactionComplete function
author: windows-driver-content
description: The SerCx2PioTransmitInitializeTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller hardware in preparation for a new PIO-transmit transaction.
old-location: serports\sercx2piotransmitinitializetransactioncomplete.htm
old-project: serports
ms.assetid: 3A2CA5FB-0844-4992-9A05-DDF9D7F1BADC
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SerCx2PioTransmitInitializeTransactionComplete, SerCx2PioTransmitInitializeTransactionComplete, SerCx2PioTransmitInitializeTransactionComplete method [Serial Ports], serports.sercx2piotransmitinitializetransactioncomplete
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
-	SerCx2PioTransmitInitializeTransactionComplete
product:
- Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---


# SerCx2PioTransmitInitializeTransactionComplete function
The <b>SerCx2PioTransmitInitializeTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller hardware in preparation for a new PIO-transmit transaction.

## Syntax

```
void SerCx2PioTransmitInitializeTransactionComplete(
  SERCX2PIOTRANSMIT PioTransmit,
  BOOLEAN           InitSuccess
);
```

## Parameters

`PioTransmit`

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a> handle to a PIO-transmit object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a> method to create this object.

`InitSuccess`

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## Return Value

None.

## Remarks

Before SerCx2 initiates a PIO-transmit transaction, SerCx2 calls the <a href="https://msdn.microsoft.com/2E3652CB-24F1-4467-AF1D-CFD52392B2DB">EvtSerCx2PioTransmitInitializeTransaction</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2PioTransmitInitializeTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2PioTransmitInitializeTransactionComplete</b> only in response to a call to the <i>EvtSerCx2PioTransmitInitializeTransaction</i> function.

For more information, see <a href="https://msdn.microsoft.com/3BEF9A3D-1FEF-4626-B07F-1670359062AF">SerCx2 PIO-Transmit Transactions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1.  |
| **Target Platform** | Universal |
| **Header** | sercx.h |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/2E3652CB-24F1-4467-AF1D-CFD52392B2DB">EvtSerCx2PioTransmitInitializeTransaction</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2PIOTRANSMIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265269">SerCx2PioTransmitCreate</a>