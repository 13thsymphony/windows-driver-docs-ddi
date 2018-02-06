---
UID: NC:sercx.EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START
title: EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START
author: windows-driver-content
description: The EvtSerCx2CustomTransmitTransactionStart event callback function is called by version 2 of the serial framework extension (SerCx2) to start a custom-transmit transaction.
old-location: serports\evtsercx2customtransmittransactionstart.htm
old-project: serports
ms.assetid: BFB2DBBE-9E00-4C1D-B336-2B9C48E98DD3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercx2customtransmittransactionstart, EvtSerCx2CustomTransmitTransactionStart callback function [Serial Ports], EvtSerCx2CustomTransmitTransactionStart, EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START, EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START, 2/EvtSerCx2CustomTransmitTransactionStart
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
-	EvtSerCx2CustomTransmitTransactionStart
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---


# EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START function
The <i>EvtSerCx2CustomTransmitTransactionStart</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to start a custom-transmit transaction.

## Syntax

```
EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START EvtSercx2CustomTransmitTransactionStart;

void EvtSercx2CustomTransmitTransactionStart(
  SERCX2CUSTOMTRANSMITTRANSACTION CustomTransmitTransaction,
  WDFREQUEST Request,
  PMDL Mdl,
  ULONG Offset,
  ULONG Length
)
{...}
```

## Parameters

`CustomTransmitTransaction`

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a> handle to a custom-transmit-transaction object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a> method to create this object.

`Request`

A handle to the framework request object associated with the custom-transmit transaction. The driver is responsible for completing this request. This request might not be the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> request sent by the client, and thus the serial controller driver should not try to use this request to access the write buffer. This request is primarily used for cancellation, completion, and queue forwarding (if needed). To access the write buffer for the client's write request, use the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.

`Mdl`

A pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> that describes the memory pages that are spanned by the write buffer for the custom-transmit transaction. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters. For more information about MDL chains, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.

`Offset`

The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.

`Length`

The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


## Return Value

None.

## Remarks

Your serial controller driver must implement this function if it creates a custom-transmit-transaction object. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a> call that creates this object.

After SerCx2 calls the <i>EvtSerCx2CustomTransmitTransactionStart</i> function, the serial controller driver initiates the transaction by programming the custom data-transfer mechanism to move data from the buffer in the write request to the transmit FIFO in the serial controller hardware. Unless the request can be completed immediately, before the <i>EvtSerCx2CustomTransmitTransactionStart</i> function returns, the driver must call a method such as <a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a> to mark the request as cancelable.

After the transaction finishes and the driver completes the pending write request, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_custom_transmit_transaction_cleanup.md">EvtSerCx2CustomTransmitTransactionCleanup</a> event callback function, if the driver implements this function.

If the serial controller driver implements an <a href="..\sercx\nc-sercx-evt_sercx2_custom_transmit_transaction_initialize.md">EvtSerCx2CustomTransmitTransactionInitialize</a> event callback function, SerCx2 calls this function before calling the <i>EvtSerCx2CustomTransmitTransactionStart</i> function. Just before the <i>EvtSerCx2CustomTransmitTransactionStart</i> call, and after the <i>EvtSerCx2CustomTransmitTransactionInitialize</i> call returns, SerCx2 starts the timer that detects whether the write request times out. For more information, see the discussion of total time-outs in <a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>.

The serial controller driver should complete the pending write request only after the last byte in the transmit FIFO has been transmitted to the serially connected peripheral device. There can be no guarantee that data written to the transmit FIFO will be transmitted without a significant delay, and a serial controller driver that assumes that such a guarantee exists can cause reliability problems for peripheral drivers.

If the custom data-transfer mechanism is a bus-master DMA device, the <i>EvtSerCx2CustomTransmitTransactionStart</i> function can call a method such as <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingoffset.md">WdfDmaTransactionInitializeUsingOffset</a> to initiate a DMA transaction that uses the write buffer described by the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters.

For more information about the <i>Mdl</i>, <i>Offset</i>, and <i>Length</i> parameters, see Remarks in <a href="..\sercx\nc-sercx-evt_sercx2_custom_transmit_transaction_initialize.md">EvtSerCx2CustomTransmitTransactionInitialize</a>.

If the request object identified by the <i>Request</i> parameter contains storage for a private context, this storage might be uninitialized the first time the serial controller driver accesses the context. On first access, the driver typically should fill the context with zeros, and then, if needed, explicitly set any fields in the context that require nonzero initial values.

For more information, see <a href="https://msdn.microsoft.com/E72E68BC-A60A-41BE-8606-92A608648042">SerCx2 Custom-Transmit Transactions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1. Available starting with Windows 8.1. |
| **Target Platform** | Desktop |
| **Header** | sercx.h |
| **IRQL** | Called at IRQL <= DISPATCH_LEVEL. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioninitializeusingoffset.md">WdfDmaTransactionInitializeUsingOffset</a>

<a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a>

<a href="..\wdfrequest\nf-wdfrequest-wdfrequestmarkcancelableex.md">WdfRequestMarkCancelableEx</a>

<a href="..\ntddser\ns-ntddser-_serial_timeouts.md">SERIAL_TIMEOUTS</a>

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>

<a href="..\sercx\nc-sercx-evt_sercx2_custom_transmit_transaction_cleanup.md">EvtSerCx2CustomTransmitTransactionCleanup</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>

<a href="..\sercx\nc-sercx-evt_sercx2_custom_transmit_transaction_initialize.md">EvtSerCx2CustomTransmitTransactionInitialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_START callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>