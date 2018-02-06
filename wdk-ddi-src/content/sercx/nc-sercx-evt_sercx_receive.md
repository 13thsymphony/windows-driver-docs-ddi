---
UID: NC:sercx.EVT_SERCX_RECEIVE
title: EVT_SERCX_RECEIVE
author: windows-driver-content
description: The EvtSerCxReceive event callback function prepares the serial controller device (UART) to do a read (receive) operation.
old-location: serports\evtsercxreceive.htm
old-project: serports
ms.assetid: C862D632-5425-4EEB-9C5D-BC3721D9F132
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercxreceive, EvtSerCxReceive callback function [Serial Ports], EvtSerCxReceive, EVT_SERCX_RECEIVE, EVT_SERCX_RECEIVE, 1/EvtSerCxReceive
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
-	EvtSerCxReceive
product: Windows
targetos: Windows
req.typenames: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR
req.product: Windows 10 or later.
---


# EVT_SERCX_RECEIVE function
The <i>EvtSerCxReceive</i> event callback function prepares the serial controller device (UART) to do a read (receive) operation.

## Syntax

```
EVT_SERCX_RECEIVE EvtSercxReceive;

NTSTATUS EvtSercxReceive(
  WDFDEVICE Device,
  size_t Length
)
{...}
```

## Parameters

`Device`

A WDFDEVICE handle to the framework device object that represents the serial controller.

`Length`

The number of bytes to be received. The controller driver can use this value as a hint to decide whether to use PIO or DMA to perform the data transfer.


## Return Value

The <i>EvtSerCxReceive</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.

## Remarks

The serial framework extension (SerCx) calls this function to configure the controller hardware to receive data. If necessary, the <i>EvtSerCxReceive</i> function can enable interrupts.

The <i>EvtSerCxReceive</i> function does not necessarily read the input data from the receive FIFO buffer. Depending on the serial controller hardware or the type of transfer, this function might set up a DMA operation to read the data, or it might schedule a transmit/receive DPC function to read the data. The serial controller driver implements this DPC function to receive data from the controller and to transmit data to the serial controller. During the DPC, the DPC function determines whether data is available to be received and, if so, uses PIO to read the data from the receive FIFO in the serial controller.

If the receive FIFO in the serial controller is empty or nearly empty, but the FIFO's high-water-mark interrupt is enabled, the DPC routine can simply return. Later, the controller driver's ISR can schedule the DPC routine to run, and this routine can read more data from the receive FIFO.

To register an <i>EvtSerCxReceive</i> callback function, the controller driver calls the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method during the <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback.

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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_RECEIVE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>