---
UID: NF:sercx.SerCx2SystemDmaTransmitInitializeTransactionComplete
title: SerCx2SystemDmaTransmitInitializeTransactionComplete function
author: windows-driver-content
description: The SerCx2SystemDmaTransmitInitializeTransactionComplete method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller hardware in preparation for a new system-DMA-transmit transaction.
old-location: serports\sercx2systemdmatransmitinitializetransactioncomplete.htm
old-project: serports
ms.assetid: B5FDD4A4-2E43-4EAD-A475-A91C60A2E925
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2SystemDmaTransmitInitializeTransactionComplete
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
req.alt-api: SerCx2SystemDmaTransmitInitializeTransactionComplete
req.alt-loc: 2.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2SystemDmaTransmitInitializeTransactionComplete function



## -description
The <b>SerCx2SystemDmaTransmitInitializeTransactionComplete</b> method notifies version 2 of the serial framework extension (SerCx2) that the serial controller driver has finished initializing the serial controller hardware in preparation for a new system-DMA-transmit transaction.



## -syntax

````
VOID SerCx2SystemDmaTransmitInitializeTransactionComplete(
  [in] SERCX2SYSTEMDMATRANSMIT SystemDmaTransmit,
  [in] BOOLEAN                 InitSuccess
);
````


## -parameters

### -param SystemDmaTransmit [in]

A <a href="serports.sercx2systemdmatransmit_object_handle">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> method to create this object.


### -param InitSuccess [in]

Whether the initialization was successful. If <b>TRUE</b>, the initialization succeeded. If <b>FALSE</b>, the initialization failed.


## -returns
None.


## -remarks
Before SerCx2 starts a system-DMA-transmit transaction, SerCx2 calls the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_initialize_transaction.md">EvtSerCx2SystemDmaTransmitInitializeTransaction</a> event callback function, if it is implemented, to initialize the serial controller to perform the transaction. In response to this call, the driver should do any initialization that is needed; then the driver must call <b>SerCx2SystemDmaTransmitInitializeTransactionComplete</b> to notify SerCx2. SerCx2 expects this notification and does not start the transaction until it is notified.

The serial controller driver must call <b>SerCx2SystemDmaTransmitInitializeTransactionComplete</b> only in response to a call to the <i>EvtSerCx2SystemDmaTransmitInitializeTransaction</i> function.

For more information, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transaction</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.1.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>2.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_transmit_initialize_transaction.md">EvtSerCx2SystemDmaTransmitInitializeTransaction</a>
</dt>
<dt>
<a href="serports.sercx2systemdmatransmit_object_handle">SERCX2SYSTEMDMATRANSMIT</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2SystemDmaTransmitInitializeTransactionComplete method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

