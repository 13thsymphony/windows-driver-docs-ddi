---
UID: NC:sercx.EVT_SERCX_TRANSMIT
title: EVT_SERCX_TRANSMIT
author: windows-driver-content
description: The EvtSerCxTransmit event callback function prepares the serial controller device (UART) to do a write (transmit) operation.
old-location: serports\evtsercxtransmit.htm
old-project: serports
ms.assetid: B32335E4-3BDF-4161-9BE2-CF3557D76988
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercxtransmit, EvtSerCxTransmit callback function [Serial Ports], EvtSerCxTransmit, EVT_SERCX_TRANSMIT, EVT_SERCX_TRANSMIT, 1/EvtSerCxTransmit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Called at IRQL <= DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	1.0\Sercx.h
apiname:
-	EvtSerCxTransmit
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---


# EVT_SERCX_TRANSMIT function
The <i>EvtSerCxTransmit</i> event callback function prepares the serial controller device (UART) to do a write (transmit) operation.

## Syntax

```
EVT_SERCX_TRANSMIT EvtSercxTransmit;

NTSTATUS EvtSercxTransmit(
  WDFDEVICE Device,
  size_t Length
)
{...}
```

## Parameters

`Device`

A WDFDEVICE handle to the framework device object that represents the serial controller.

`Length`

The number of bytes to be transmitted. The controller driver can use this value as a hint to decide whether to use PIO or DMA to perform the data transfer.


## Return Value

The <i>EvtSerCxTransmit</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.

## Remarks

The serial framework extension (SerCx) calls this function to configure the serial controller hardware to transmit data. If necessary, the <i>EvtSerCxTransmit</i> function can enable interrupts.

The <i>EvtSerCxTransmit</i> function does not necessarily write the output data to the transmit FIFO buffer. Depending on the serial controller hardware or the type of transfer, this function might set up a DMA operation to write the data, or it might schedule a transmit/receive DPC function to write the data. The serial controller driver implements this DPC function to transmit data to the serial controller and to receive data from the controller. During the DPC, the DPC function determines whether data is available to be transmitted and, if so, uses PIO to transfer the data to the transmit FIFO in the serial controller.

If the transmit FIFO in the serial controller is full or nearly full, but the FIFO's low-water-mark interrupt is enabled, the <i>EvtSerCxTransmit</i> function can simply return. Later, the controller driver's ISR can schedule the transmit/receive DPC function to run, and this function can transfer more output data to the transmit FIFO.

To register an <i>EvtSerCxTransmit</i> callback function, the controller driver calls the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method during the <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Target Platform** | Desktop |
| **Header** | sercx.h |
| **IRQL** | Called at IRQL <= DISPATCH_LEVEL |

## See Also

<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

<a href="..\wdfdpc\nf-wdfdpc-wdfdpcenqueue.md">WdfDpcEnqueue</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_TRANSMIT callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>