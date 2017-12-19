---
UID: NC.sercx.EVT_SERCX_FILEOPEN
title: EVT_SERCX_FILEOPEN
author: windows-driver-content
description: The EvtSerCxFileOpen event callback function notifies the serial controller driver that a client opened a file handle on the serial controller device and that a file object has been created to represent the device.
old-location: serports\evtsercxfileopen.htm
old-project: serports
ms.assetid: 90D08857-69E0-4DD9-9588-86900466E8DE
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SENSOR_VALUE_PAIR, PSENSOR_VALUE_PAIR, *PSENSOR_VALUE_PAIR, SENSOR_VALUE_PAIR
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
req.alt-api: EvtSerCxFileOpen
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

# EVT_SERCX_FILEOPEN callback



## -description
The <i>EvtSerCxFileOpen</i> event callback function notifies the serial controller driver that a client opened a file handle on the serial controller device and that a file object has been created to represent the device.



## -prototype

````
EVT_SERCX_FILEOPEN EvtSerCxFileOpen;

NTSTATUS EvtSerCxFileOpen(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters

### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the serial controller.


## -returns
The <i>EvtSerCxFileOpen</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.


## -remarks
The serial framework extension (SerCx) calls this function to prepare the serial controller hardware to accept requests for I/O operations. This function should configure the controller in a state in which it is ready to receive and transmit data. If interrupts are required, this function should enable interrupts. In addition, this function should allocate any memory that is required only during the lifetime of the file object. For example, this function can allocate an interrupt data buffer.

To register an <i>EvtSerCxFileOpen</i> callback function, the driver must call the <a href="serports.sercxinitialize">SerCxInitialize</a> method.

For more information, see <a href="kmdf.framework_file_objects">Framework File Objects</a>.

The function type for this callback is declared in Sercx.h, as follows.

To define an <i>EvtSerCxFileOpen</i> callback function that is named <code>MyEvtSerCxFileOpen</code>, you must first provide a function declaration that <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV) and other verification tools require, as follows.

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
<a href="serports.sercxinitialize">SerCxInitialize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20EVT_SERCX_FILEOPEN callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

