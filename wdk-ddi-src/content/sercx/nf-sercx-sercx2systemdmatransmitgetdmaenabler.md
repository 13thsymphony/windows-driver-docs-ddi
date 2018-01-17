---
UID: NF:sercx.SerCx2SystemDmaTransmitGetDmaEnabler
title: SerCx2SystemDmaTransmitGetDmaEnabler function
author: windows-driver-content
description: The SerCx2SystemDmaTransmitGetDmaEnabler method gets the DMA enabler for the system DMA controller that is used for system-DMA-transmit transactions.
old-location: serports\sercx2systemdmatransmitgetdmaenabler.htm
old-project: serports
ms.assetid: 5B6893D4-51ED-483C-87F4-0404C48E100F
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SerCx2SystemDmaTransmitGetDmaEnabler
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
req.alt-api: SerCx2SystemDmaTransmitGetDmaEnabler
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
req.typenames: *PSERCX_STATUS, SERCX_STATUS
req.product: Windows 10 or later.
---

# SerCx2SystemDmaTransmitGetDmaEnabler function



## -description
The <b>SerCx2SystemDmaTransmitGetDmaEnabler</b> method gets the DMA enabler for the system DMA controller that is used for system-DMA-transmit transactions.



## -syntax

````
WDFDMAENABLER SerCx2SystemDmaTransmitGetDmaEnabler(
  [in] SERCX2SYSTEMDMATRANSMIT SystemDmaTransmit
);
````


## -parameters

### -param SystemDmaTransmit [in]

A <a href="serports.sercx2systemdmatransmit_object_handle">SERCX2SYSTEMDMATRANSMIT</a> handle to a system-DMA-transmit object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> method to create this object.


## -returns
This method returns a WDFDMAENABLER handle to the framework DMA enabler object that represents the system DMA controller that is used for system-DMA-transmit transactions.


## -remarks
If necessary, your serial controller driver can call this method to configure special features in the system DMA controller. The driver can use the DMA enabler returned by this method to specify DMA settings that were not supplied in the <a href="..\sercx\ns-sercx-_sercx2_system_dma_transmit_config.md">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a> structure that the driver previously passed as an input parameter to the <a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a> method. Or, the driver can use the DMA enabler to change the DMA settings that were previously specified in this structure.

For more information about DMA enabler objects, see <a href="https://msdn.microsoft.com/87735776-c371-425b-bc53-0c68375c9562">Enabling DMA Transactions</a>. For more information about system-DMA-transmit transactions, see <a href="https://msdn.microsoft.com/8569E76F-CAFF-4A2C-8052-62B340C5ADED">SerCx2 System-DMA-Transmit Transactions</a>.


## -see-also
<dl>
<dt>
<a href="serports.sercx2systemdmatransmit_object_handle">SERCX2SYSTEMDMATRANSMIT</a>
</dt>
<dt>
<a href="..\sercx\ns-sercx-_sercx2_system_dma_transmit_config.md">SERCX2_SYSTEM_DMA_TRANSMIT_CONFIG</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2systemdmatransmitcreate.md">SerCx2SystemDmaTransmitCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2SystemDmaTransmitGetDmaEnabler method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

