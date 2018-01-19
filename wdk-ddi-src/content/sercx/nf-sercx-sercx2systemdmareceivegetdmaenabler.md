---
UID : NF:sercx.SerCx2SystemDmaReceiveGetDmaEnabler
title : SerCx2SystemDmaReceiveGetDmaEnabler function
author : windows-driver-content
description : The SerCx2SystemDmaReceiveGetDmaEnabler method gets the DMA enabler for the system DMA controller that is used for system-DMA-receive transactions.
old-location : serports\sercx2systemdmareceivegetdmaenabler.htm
old-project : serports
ms.assetid : 0C1CEDD8-EA78-4188-AD05-99608B400C84
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : SerCx2SystemDmaReceiveGetDmaEnabler
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
req.alt-api : SerCx2SystemDmaReceiveGetDmaEnabler
req.alt-loc : 2.0\Sercx.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : SERCX_STATUS, *PSERCX_STATUS
req.product : Windows 10 or later.
---


# SerCx2SystemDmaReceiveGetDmaEnabler function
The <b>SerCx2SystemDmaReceiveGetDmaEnabler</b> method gets the DMA enabler for the system DMA controller that is used for system-DMA-receive transactions.

## Syntax

````
WDFDMAENABLER SerCx2SystemDmaReceiveGetDmaEnabler(
  [in] SERCX2SYSTEMDMARECEIVE SystemDmaReceive
);
````

## Parameters

`SystemDmaReceive`

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> method to create this object.


## Return Value

This method returns a WDFDMAENABLER handle to the framework DMA enabler object that represents the system DMA controller that is used for system-DMA-receive transactions.

## Remarks

If necessary, your serial controller driver can call this method to configure special features in the system DMA controller. The driver can use the DMA enabler returned by this method to specify DMA settings that were not supplied in the <a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure that the driver previously passed as an input parameter to the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> method. Or, the driver can use the DMA enabler to change the DMA settings that were previously specified in this structure.

For more information about DMA enabler objects, see <a href="https://msdn.microsoft.com/87735776-c371-425b-bc53-0c68375c9562">Enabling DMA Transactions</a>. For more information about system-DMA-receive transactions, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265343">SerCx2 System-DMA-Receive Transactions</a>.

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

<dl>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>
</dt>
<dt>
<a href="..\sercx\ns-sercx-_sercx2_system_dma_receive_config.md">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SerCx2SystemDmaReceiveGetDmaEnabler method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>