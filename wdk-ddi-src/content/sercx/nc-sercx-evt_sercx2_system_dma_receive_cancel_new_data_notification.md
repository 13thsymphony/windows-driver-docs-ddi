---
UID : NC:sercx.EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION
title : EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION
author : windows-driver-content
description : The EvtSerCx2SystemDmaReceiveCancelNewDataNotification event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a new-data notification that SerCx2 enabled in a previous call to the EvtSerCx2SystemDmaReceiveEnableNewDataNotification event callback function.
old-location : serports\evtsercx2systemdmareceivecancelnewdatanotification.htm
old-project : serports
ms.assetid : 7C88F794-0C2B-4715-B09A-2AA49414F18A
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : serports.evtsercx2systemdmareceivecancelnewdatanotification, EvtSerCx2SystemDmaReceiveCancelNewDataNotification callback function [Serial Ports], EvtSerCx2SystemDmaReceiveCancelNewDataNotification, EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION, EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION, 2/EvtSerCx2SystemDmaReceiveCancelNewDataNotification
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
req.typenames : SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product : Windows 10 or later.
---


# EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION function
The <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to cancel a new-data notification that SerCx2 enabled in a previous call to the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification.md">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a> event callback function.

## Syntax

```
EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION EvtSercx2SystemDmaReceiveCancelNewDataNotification;

BOOLEAN EvtSercx2SystemDmaReceiveCancelNewDataNotification(
  SERCX2SYSTEMDMARECEIVE SystemDmaReceive
)
{...}
```

## Parameters

`SystemDmaReceive`

A <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a> handle to a system-DMA-receive object. The serial controller driver previously called the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> method to create this object.


## Return Value

The <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> function returns <b>TRUE</b> if the new-data notification was successfully canceled  and the serial controller driver can guarantee that this notification will not cause the <a href="..\sercx\nf-sercx-sercx2systemdmareceivenewdatanotification.md">SerCx2SystemDmaReceiveNewDataNotification</a> method to be called. The function returns <b>FALSE</b> if the driver has already called the <b>SerCx2SystemDmaReceiveNewDataNotification</b> method, or is about to call this method.

## Remarks

Your serial controller driver can, as an option, implement this function. If implemented, the driver registers the function in the <a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a> call that creates the system-DMA-receive object. A driver that implements this function must also implement an <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification.md">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a> event callback function.

If the associated read request times out or is canceled while a new-data notification request is pending, SerCx2 calls the <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> function to cancel the pending notification. If this call returns <b>FALSE</b>, SerCx2 expects the serial controller driver to call <a href="..\sercx\nf-sercx-sercx2systemdmareceivenewdatanotification.md">SerCx2SystemDmaReceiveNewDataNotification</a>; only after this call does SerCx2 call the <a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_cleanup_transaction.md">EvtSerCx2SystemDmaReceiveCleanupTransaction</a> function, if it is implemented, and complete the request.

To cancel the new-data notification, the <i>EvtSerCx2SystemDmaReceiveCancelNewDataNotification</i> function typically disables the interrupt in the serial controller that indicates that more data is available to be read from the receive FIFO. This interrupt was enabled by a previous call to the <i>EvtSerCx2SystemDmaReceiveEnableNewDataNotification</i> function.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn265343">SerCx2 System-DMA-Receive Transactions</a>.

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

<a href="..\sercx\nf-sercx-sercx2systemdmareceivenewdatanotification.md">SerCx2SystemDmaReceiveNewDataNotification</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/serports/sercx2-object-handles">SERCX2SYSTEMDMARECEIVE</a>

<a href="..\sercx\nc-sercx-evt_sercx2_system_dma_receive_enable_new_data_notification.md">EvtSerCx2SystemDmaReceiveEnableNewDataNotification</a>

<a href="..\sercx\nf-sercx-sercx2systemdmareceivecreate.md">SerCx2SystemDmaReceiveCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_SYSTEM_DMA_RECEIVE_CANCEL_NEW_DATA_NOTIFICATION callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>