---
UID : NC:sercx.EVT_SERCX2_PURGE_FIFOS
title : EVT_SERCX2_PURGE_FIFOS
author : windows-driver-content
description : The EvtSerCx2PurgeFifos event callback function is called by version 2 of the serial framework extension (SerCx2) to purge the FIFO buffers in the serial controller hardware.
old-location : serports\evtsercx2purgefifos.htm
old-project : serports
ms.assetid : 52875B36-F52B-4D29-9C9D-76DB12BFEEA6
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : serports.evtsercx2purgefifos, EvtSerCx2PurgeFifos callback function [Serial Ports], EvtSerCx2PurgeFifos, EVT_SERCX2_PURGE_FIFOS, EVT_SERCX2_PURGE_FIFOS, 2/EvtSerCx2PurgeFifos
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
req.irql : Called at PASSIVE_LEVEL.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product : Windows 10 or later.
---


# EVT_SERCX2_PURGE_FIFOS function
The <i>EvtSerCx2PurgeFifos</i> event callback function is called by version 2 of the serial framework extension (SerCx2) to purge the FIFO buffers in the serial controller hardware.

## Syntax

```
EVT_SERCX2_PURGE_FIFOS EvtSercx2PurgeFifos;

void EvtSercx2PurgeFifos(
  WDFDEVICE Device,
  BOOLEAN PurgeRxFifo,
  BOOLEAN PurgeTxFifo
)
{...}
```

## Parameters

`Device`

A WDFDEVICE handle to the framework device object that represents the serial controller. The serial controller driver created this object in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function. For more information, see <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>.

`PurgeRxFifo`

Whether to purge the receive FIFO. If this parameter is set to <b>TRUE</b>, purge the receive FIFO. If <b>FALSE</b>, do not purge the receive FIFO.

`PurgeTxFifo`

Whether to purge the transmit FIFO. If this parameter is set to <b>TRUE</b>, purge the transmit FIFO. If <b>FALSE</b>, do not purge the transmit FIFO.


## Return Value

None.

## Remarks

Your serial controller driver must implement this function. The driver registers the function in the call to the <a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a> method that finishes the initialization of the framework device object for the serial controller.

SerCx2 calls the <i>EvtSerCx2PurgeFifos</i> function when a client (peripheral driver) sends an <a href="..\ntddser\ni-ntddser-ioctl_serial_purge.md">IOCTL_SERIAL_PURGE</a> control request that requires either one or both of the FIFO buffers in the serial controller hardware to be purged. If the <b>IOCTL_SERIAL_PURGE</b> control request requires pending read or write (<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>) requests to be canceled, SerCx2 cancels these requests before it calls the <i>EvtSerCx2PurgeFifos</i> function.

SerCx2 also calls the <i>EvtSerCx2PurgeFifos</i> function when a client opens a logical connection to the serial controller device and obtains a file handle to this connection. For more information, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | sercx.h |
| **Library** |  |
| **IRQL** | Called at PASSIVE_LEVEL. |
| **DDI compliance rules** |  |

## See Also

<a href="..\sercx\nf-sercx-sercx2initializedevice.md">SerCx2InitializeDevice</a>

<a href="..\ntddser\ni-ntddser-ioctl_serial_purge.md">IOCTL_SERIAL_PURGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX2_PURGE_FIFOS callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>