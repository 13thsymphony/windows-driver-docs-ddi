---
UID: NC:sercx.EVT_SERCX_TRANSMIT_CANCEL
title: EVT_SERCX_TRANSMIT_CANCEL
author: windows-driver-content
description: The EvtSerCxTransmitCancel event callback function notifies the serial controller driver that the pending transmit request is canceled.
old-location: serports\evtsercxtransmitcancel.htm
old-project: serports
ms.assetid: 7922A3BD-8829-42A3-9F94-3C26F1262626
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercxtransmitcancel, EvtSerCxTransmitCancel callback function [Serial Ports], EvtSerCxTransmitCancel, EVT_SERCX_TRANSMIT_CANCEL, EVT_SERCX_TRANSMIT_CANCEL, 1/EvtSerCxTransmitCancel
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
-	EvtSerCxTransmitCancel
product: Windows
targetos: Windows
req.typenames: "*PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR"
req.product: Windows 10 or later.
---


# EVT_SERCX_TRANSMIT_CANCEL function
The <i>EvtSerCxTransmitCancel</i> event callback function notifies the serial controller driver that the pending transmit request is canceled.

## Syntax

```
EVT_SERCX_TRANSMIT_CANCEL EvtSercxTransmitCancel;

void EvtSercxTransmitCancel(
  WDFDEVICE Device
)
{...}
```

## Parameters

`Device`

A WDFDEVICE handle to the framework device object that represents the serial controller.


## Return Value

None.

## Remarks

The serial framework extension (SerCx) calls this function to inform the serial controller driver that the current transmit request has been canceled.  If the driver has an outstanding transmit operation in progress, the driver should cancel this operation and call the <a href="..\sercx\nf-sercx-sercxprogresstransmit.md">SerCxProgressTransmit</a> method to report the cancellation. In the <b>SerCxProgressTransmit</b> call, set <i>BytesTransmitted</i> to the number of bytes transmitted before the operation was canceled, and set <i>TransmitStatus</i> to <b>SerCxStatusCancelled</b>.

To register an <i>EvtSerCxTransmitCancel</i> callback function, the driver must call the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
  EVT_SERCX_TRANSMIT_CANCEL(
    __in WDFDEVICE Device
    );</pre>
</td>
</tr>
</table></span></div>
To define an <i>EvtSerCxTransmitCancel</i> callback function that is named <code>MyEvtSerCxTransmitCancel</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX_TRANSMIT_CANCEL MyEvtSerCxTransmitCancel;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
  MyEvtSerCxTransmitCancel(
    __in WDFDEVICE Device
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
For more information about SDV requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions Using Function Role Types for KMDF Drivers</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.  |
| **Target Platform** | Desktop |
| **Header** | sercx.h |
| **IRQL** | Called at IRQL <= DISPATCH_LEVEL |