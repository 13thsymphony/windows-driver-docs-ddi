---
UID: NF.wdfdevice.WdfDeviceGetDeviceStackIoType
title: WdfDeviceGetDeviceStackIoType function
author: windows-driver-content
description: The WdfDeviceGetDeviceStackIoType method retrieves the buffer access methods that the framework is using for a device.
old-location: wdf\wdfdevicegetdevicestackiotype.htm
old-project: wdf
ms.assetid: E697F53C-2642-4E3F-AA8C-D0802B39D187
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfDeviceGetDeviceStackIoType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.alt-api: WdfDeviceGetDeviceStackIoType
req.alt-loc: WUDFx02000.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WdfDeviceGetDeviceStackIoType function



## -description
<p class="CCE_Message">[Applies to UMDF only]
The <b>WdfDeviceGetDeviceStackIoType</b> method retrieves the buffer access methods that the framework is using for a device.


## -syntax

````
void WdfDeviceGetDeviceStackIoType(
  _In_  WDFDEVICE          Device,
  _Out_ WDF_DEVICE_IO_TYPE *ReadWriteIoType,
  _Out_ WDF_DEVICE_IO_TYPE *IoControlIoType
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.

### -param ReadWriteIoType [out]

A pointer to a driver-allocated location that receives a <a href="wdf.wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>-typed value. This value identifies the buffer access method that the framework is using for a device's read and write requests.

### -param IoControlIoType [out]

A pointer to a driver-allocated location that receives a <a href="wdf.wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>-typed value. This value that identifies the buffer access method that the framework is using for a device's I/O control requests.

## -returns
This method does not return a value.

## -remarks
If your driver calls <b>WdfDeviceGetDeviceStackIoType</b> before the PnP manager has loaded all of the device's drivers, the values that <b>WdfDeviceGetDeviceStackIoType</b> retrieves might not be the values that it actually uses.

For more information about how the framework chooses a buffer access method, see <a href="wdf.managing_buffer_access_methods_in_umdf_drivers">Managing Buffer Access Methods in UMDF Drivers</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum support
</th>
<td width="70%">
Windows 8.1
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>WUDFx02000.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>WUDFx02000.dll; </dt>
<dt>TBD</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetDeviceStackIoType method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
