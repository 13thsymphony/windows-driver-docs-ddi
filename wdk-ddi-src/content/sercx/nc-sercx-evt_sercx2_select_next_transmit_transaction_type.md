---
UID : NC:sercx.EVT_SERCX2_SELECT_NEXT_TRANSMIT_TRANSACTION_TYPE
title : EVT_SERCX2_SELECT_NEXT_TRANSMIT_TRANSACTION_TYPE
author : windows-driver-content
description : The EvtSerCx2SelectNextTransmitTransactionType event callback function is called by version 2 of the serial framework extension (SerCx2) to determine which data-transfer mechanism to use for the next write operation.
old-location : serports\evtsercx2selectnexttransmittransactiontype.htm
old-project : serports
ms.assetid : EE46CB43-18BA-4FD7-A60D-07DB1760B8E7
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : serports.evtsercx2selectnexttransmittransactiontype, EvtSerCx2SelectNextTransmitTransactionType callback function [Serial Ports], EvtSerCx2SelectNextTransmitTransactionType, EVT_SERCX2_SELECT_NEXT_TRANSMIT_TRANSACTION_TYPE, EVT_SERCX2_SELECT_NEXT_TRANSMIT_TRANSACTION_TYPE, 2/EvtSerCx2SelectNextTransmitTransactionType
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


# EVT_SERCX2_SELECT_NEXT_TRANSMIT_TRANSACTION_TYPE function
The <i>EvtSerCx2SelectNextTransmitTransactionType</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to determine which data-transfer mechanism to use for the next write operation.

## Syntax

```
EVT_SERCX2_SELECT_NEXT_TRANSMIT_TRANSACTION_TYPE EvtSercx2SelectNextTransmitTransactionType;

SERCX2_TRANSACTION_TYPE EvtSercx2SelectNextTransmitTransactionType(
  WDFDEVICE Device,
  PMDL Mdl,
  ULONG Offset,
  ULONG RemainingLength,
  SERCX2CUSTOMTRANSMIT * CustomTransmit,
  PULONG NextTransactionLength
)
{...}
```

## Parameters

`Device`

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>.

`Mdl`

A pointer to an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> that describes the memory pages that are spanned by the write buffer for the next transmit transaction. The scatter/gather list for the DMA transfer will use the region of this memory that is specified by the <i>Offset</i> and <i>Length</i> parameters.

`Offset`

The starting offset for the next data transfer. This parameter is a byte offset from the start of the buffer region described by the MDL. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Offset</i> are in the range 0 to N–1.

`RemainingLength`

The total number of bytes of data that remain to be transferred in the current write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) request. If the MDL specifies a total of N bytes of buffer space, possible values of <i>Length</i> are in the range 1 to N–<i>Offset</i>.

`CustomTransmit`

A pointer to a location to which the function writes the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMTRANSMIT</a> handle to the custom-transmit object. If the function returns <b>SerCx2TransactionTypeCustom</b>, the function must supply the object handle that the serial controller driver created in a previous call to the <a href="..\sercx\nf-sercx-sercx2customtransmitcreate.md">SerCx2CustomTransmitCreate</a> method. If the return value is not <b>SerCx2TransactionTypeCustom</b>, this output value is ignored by SerCx2.

`NextTransactionLength`

A pointer to a location to which the function writes the number of bytes to transfer in the next transmit transaction. If the return value is <b>SerCx2TransactionTypeDefault</b>, this output value is ignored by SerCx2.


## Return Value

The <i>EvtSerCx2SelectNextTransmitTransactionType</i> function returns a <a href="..\sercx\ne-sercx-_sercx2_transaction_type.md">SERCX2_TRANSACTION_TYPE</a> enumeration constant to indicate whether to use a driver-selected transaction type (programmed I/O (PIO), system DMA, or custom data transfer), or to let SerCx2 choose which transaction type to use for the next transmit transaction.

## Remarks

Your serial controller driver can, as an option, implement this function. If implemented, the driver registers this function in the call to the <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

If your serial controller driver does not implement an <i>EvtSerCx2SelectNextTransmitTransactionType</i> function, then SerCx2 always decides what type of data-transfer mechanism (PIO, system DMA, or custom) to use for the next transmit transaction. SerCx2 bases its decisions on the I/O configuration information supplied by the serial controller driver. A driver that supports system-DMA-transmit transactions supplies a <a href="..\sercx\ns-sercx-_sercx2_system_dma_transmit_config.md">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure that contains this information. A driver that supports custom-transmit transactions supplies a <a href="..\sercx\ns-sercx-_sercx2_custom_transmit_config.md">SERCX2_CUSTOM_TRANSMIT_CONFIG</a> structure that contains this information.

If your serial controller driver implements an <i>EvtSerCx2SelectNextTransmitTransactionType</i> function, SerCx2 calls this function to determine what type of data-transfer mechanism (PIO, system DMA, or custom) to use for the next transmit transaction. You might want to implement this function if the serial controller has special hardware capabilities that cannot adequately be described by the I/O configuration information in the <b>SERCX2_<i>XXX</i>_TRANSMIT_CONFIG</b> structures.
<div class="alert"><b>Note</b>  Even if a serial controller driver implements an <i>EvtSerCx2SelectNextTransmitTransactionType</i> function, SerCx2 uses PIO-transmit transactions to perform certain types of data transfers without first calling this function.</div><div> </div>For more information, see <a href="https://msdn.microsoft.com/04DDFE53-4855-4029-BE1E-9D184B02A998">Overview of SerCx2 I/O Transactions</a>.

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

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

<a href="..\sercx\nf-sercx-sercx2customtransmitcreate.md">SerCx2CustomTransmitCreate</a>

<a href="..\sercx\ns-sercx-_sercx2_system_dma_transmit_config.md">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>

<a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>

<a href="..\sercx\ns-sercx-_sercx2_custom_transmit_config.md">SERCX2_CUSTOM_TRANSMIT_CONFIG</a>

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>

<a href="..\sercx\ne-sercx-_sercx2_transaction_type.md">SERCX2_TRANSACTION_TYPE</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2CUSTOMTRANSMIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_SELECT_NEXT_TRANSMIT_TRANSACTION_TYPE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>