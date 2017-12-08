---
UID: NC.sercx.EVT_SERCX_TRANSMIT
title: EVT_SERCX_TRANSMIT
author: windows-driver-content
description: The EvtSerCxTransmit event callback function prepares the serial controller device (UART) to do a write (transmit) operation.
old-location: serports\evtsercxtransmit.htm
old-project: serports
ms.assetid: B32335E4-3BDF-4161-9BE2-CF3557D76988
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: SENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
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
req.alt-api: EvtSerCxTransmit
req.alt-loc: 1.0\Sercx.h
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
req.product: Windows 10 or later.
---

# EVT_SERCX_TRANSMIT callback



## -description
The <i>EvtSerCxTransmit</i> event callback function prepares the serial controller device (UART) to do a write (transmit) operation.


## -prototype

````
EVT_SERCX_TRANSMIT EvtSerCxTransmit;

NTSTATUS EvtSerCxTransmit(
  _In_ WDFDEVICE Device,
  _In_ size_t    Length
)
{ ... }
````


## -parameters

### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.

### -param Length [in]

The number of bytes to be transmitted. The controller driver can use this value as a hint to decide whether to use PIO or DMA to perform the data transfer.

## -returns
The <i>EvtSerCxTransmit</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.

## -remarks
The serial framework extension (SerCx) calls this function to configure the serial controller hardware to transmit data. If necessary, the <i>EvtSerCxTransmit</i> function can enable interrupts.

The <i>EvtSerCxTransmit</i> function does not necessarily write the output data to the transmit FIFO buffer. Depending on the serial controller hardware or the type of transfer, this function might set up a DMA operation to write the data, or it might schedule a transmit/receive DPC function to write the data. The serial controller driver implements this DPC function to transmit data to the serial controller and to receive data from the controller. During the DPC, the DPC function determines whether data is available to be transmitted and, if so, uses PIO to transfer the data to the transmit FIFO in the serial controller.

If the transmit FIFO in the serial controller is full or nearly full, but the FIFO's low-water-mark interrupt is enabled, the <i>EvtSerCxTransmit</i> function can simply return. Later, the controller driver's ISR can schedule the transmit/receive DPC function to run, and this function can transfer more output data to the transmit FIFO.

To register an <i>EvtSerCxTransmit</i> callback function, the controller driver calls the <a href="serports.sercxinitialize">SerCxInitialize</a> method during the <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback.

The function type for this callback is declared in Sercx.h, as follows.

To define an <i>EvtSerCxTransmit</i> callback function that is named <code>MyEvtSerCxTransmit</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

Then, implement your callback function as follows.

For more information about SDV requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available starting with Windows 8.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>1.0\Sercx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
Called at IRQL &lt;= DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>
</dt>
<dt>
<a href="serports.sercxinitialize">SerCxInitialize</a>
</dt>
<dt>
<a href="kmdf.wdfdpcenqueue">WdfDpcEnqueue</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_TRANSMIT callback function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
