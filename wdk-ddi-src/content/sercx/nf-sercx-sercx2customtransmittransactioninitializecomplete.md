---
UID: NF:sercx.SerCx2CustomTransmitTransactionInitializeComplete
title: SerCx2CustomTransmitTransactionInitializeComplete function
author: windows-driver-content
description: The SerCx2CustomTransmitTransactionInitializeComplete method informs version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller and associated hardware in preparation for a new custom-transmit transaction.
old-location: serports\sercx2customtransmittransactioninitializecomplete.htm
old-project: serports
ms.assetid: 5C2BF433-11C0-425A-B14A-7A0275F7DF51
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SerCx2CustomTransmitTransactionInitializeComplete, SerCx2CustomTransmitTransactionInitializeComplete, SerCx2CustomTransmitTransactionInitializeComplete method [Serial Ports], serports.sercx2customtransmittransactioninitializecomplete
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
-	SerCx2CustomTransmitTransactionInitializeComplete
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---


# SerCx2CustomTransmitTransactionInitializeComplete function
The <b>SerCx2CustomTransmitTransactionInitializeComplete</b> method informs version 2 of the serial framework extension (SerCx2) that the serial driver has finished initializing the serial controller and associated hardware in preparation for a new custom-transmit transaction.

## Syntax

```
void SerCx2CustomTransmitTransactionInitializeComplete(
  SERCX2CUSTOMTRANSMITTRANSACTION CustomTransmitTransaction,
  BOOLEAN                         InitSuccess
);
```

## Parameters

`CustomTransmitTransaction`

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a> handle to a custom-transmit object. The serial controller driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265259">SerCx2CustomTransmitTransactionCreate</a> method to create this object.

`InitSuccess`

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## Return Value

None.

## Remarks

Before SerCx2 starts a custom-transmit transaction, SerCx2 calls the <a href="https://msdn.microsoft.com/CFC577D6-747F-4752-8CB6-7410C21487B6">EvtSerCx2CustomTransmitTransactionInitialize</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should first do any initialization that is needed; then the driver must call <b>SerCx2CustomTransmitTransactionInitializeComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2CustomTransmitTransactionInitializeComplete</b> only in response to a call to the <i>EvtSerCx2CustomTransmitTransactionInitialize</i> function.

For more information, see <a href="https://msdn.microsoft.com/E72E68BC-A60A-41BE-8606-92A608648042">SerCx2 Custom-Transmit Transactions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1.  |
| **Target Platform** | Universal |
| **Header** | sercx.h |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/CFC577D6-747F-4752-8CB6-7410C21487B6">EvtSerCx2CustomTransmitTransactionInitialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265259">SerCx2CustomTransmitTransactionCreate</a>