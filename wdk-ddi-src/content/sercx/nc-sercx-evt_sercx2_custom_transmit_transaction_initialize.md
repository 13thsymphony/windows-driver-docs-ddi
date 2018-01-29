---
UID : NC:sercx.EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE
title : EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE
author : windows-driver-content
description : The EvtSerCx2CustomTransmitTransactionInitialize event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller driver to perform a custom-transmit transaction.
old-location : serports\evtsercx2customtransmittransactioninitialize.htm
old-project : serports
ms.assetid : CFC577D6-747F-4752-8CB6-7410C21487B6
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : serports.evtsercx2customtransmittransactioninitialize, EvtSerCx2CustomTransmitTransactionInitialize callback function [Serial Ports], EvtSerCx2CustomTransmitTransactionInitialize, EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE, EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE, 2/EvtSerCx2CustomTransmitTransactionInitialize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : sercx.h
req.include-header : 
req.target-type : Desktop
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
req.lib : 
req.dll : 
req.irql : Called at IRQL <= DISPATCH_LEVEL.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR"
req.product : Windows 10 or later.
---


# EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE function
The <i>EvtSerCx2CustomTransmitTransactionInitialize</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to prepare the serial controller driver to perform a custom-transmit transaction.

## Syntax

```
EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE EvtSercx2CustomTransmitTransactionInitialize;

void EvtSercx2CustomTransmitTransactionInitialize(
  SERCX2CUSTOMTRANSMITTRANSACTION CustomTransmitTransaction,
  PMDL Mdl,
  ULONG Offset,
  ULONG Length
)
{...}
```

## Parameters

`CustomTransmitTransaction`

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a> handle to a custom-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a> method to create this object.

`Mdl`

A pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> that describes the memory pages that are spanned by the write buffer for the custom-transmit transaction. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.

`Offset`

The starting offset for the data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.

`Length`

The size, in bytes, of the data transfer. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.


## Return Value

None.

## Remarks

Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a> call that creates the custom-transmit object.

Your driver should implement an <i>EvtSerCx2CustomTransmitTransactionInitialize</i> function if it needs to initialize the serial controller and associated hardware in preparation for a new custom-transmit transaction. SerCx2 calls this function, if it is implemented, before starting the custom-transmit transaction. In response to this call, the serial controller driver must call the <a href="..\sercx\nf-sercx-sercx2customtransmittransactioninitializecomplete.md">SerCx2CustomTransmitTransactionInitializeComplete</a> method to notify SerCx2 after the initialization is finished.

For more information, see <a href="https://msdn.microsoft.com/E72E68BC-A60A-41BE-8606-92A608648042">SerCx2 Custom-Transmit Transactions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sercx.h |
| **Library** |  |
| **IRQL** | Called at IRQL <= DISPATCH_LEVEL. |
| **DDI compliance rules** |  |

## See Also

<a href="..\sercx\nf-sercx-sercx2customtransmittransactioncreate.md">SerCx2CustomTransmitTransactionCreate</a>

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265257">SERCX2CUSTOMTRANSMITTRANSACTION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_CUSTOM_TRANSMIT_TRANSACTION_INITIALIZE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>