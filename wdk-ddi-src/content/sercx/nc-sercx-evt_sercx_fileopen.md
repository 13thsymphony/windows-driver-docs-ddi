---
UID: NC:sercx.EVT_SERCX_FILEOPEN
title: EVT_SERCX_FILEOPEN
author: windows-driver-content
description: The EvtSerCxFileOpen event callback function notifies the serial controller driver that a client opened a file handle on the serial controller device and that a file object has been created to represent the device.
old-location: serports\evtsercxfileopen.htm
old-project: serports
ms.assetid: 90D08857-69E0-4DD9-9588-86900466E8DE
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.evtsercxfileopen, EvtSerCxFileOpen callback function [Serial Ports], EvtSerCxFileOpen, EVT_SERCX_FILEOPEN, EVT_SERCX_FILEOPEN, 1/EvtSerCxFileOpen
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
-	EvtSerCxFileOpen
product: Windows
targetos: Windows
req.typenames: "*PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR"
req.product: Windows 10 or later.
---


# EVT_SERCX_FILEOPEN function
The <i>EvtSerCxFileOpen</i> event callback function notifies the serial controller driver that a client opened a file handle on the serial controller device and that a file object has been created to represent the device.

## Syntax

```
EVT_SERCX_FILEOPEN EvtSercxFileopen;

NTSTATUS EvtSercxFileopen(
  WDFDEVICE Device
)
{...}
```

## Parameters

`Device`

A WDFDEVICE handle to the framework device object that represents the serial controller.


## Return Value

The <i>EvtSerCxFileOpen</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.

## Remarks

The serial framework extension (SerCx) calls this function to prepare the serial controller hardware to accept requests for I/O operations. This function should configure the controller in a state in which it is ready to receive and transmit data. If interrupts are required, this function should enable interrupts. In addition, this function should allocate any memory that is required only during the lifetime of the file object. For example, this function can allocate an interrupt data buffer.

To register an <i>EvtSerCxFileOpen</i> callback function, the driver must call the <a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a> method.

For more information, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.


#### Examples

The function type for this callback is declared in Sercx.h, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS
  EVT_SERCX_FILEOPEN(
    __in WDFDEVICE Device
    );</pre>
</td>
</tr>
</table></span></div>
To define an <i>EvtSerCxFileOpen</i> callback function that is named <code>MyEvtSerCxFileOpen</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_SERCX_FILEOPEN MyEvtSerCxFileOpen;</pre>
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
<pre>NTSTATUS
  MyEvtSerCxFileOpen(
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

## See Also

<a href="..\sercx\nf-sercx-sercxinitialize.md">SerCxInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_FILEOPEN callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>