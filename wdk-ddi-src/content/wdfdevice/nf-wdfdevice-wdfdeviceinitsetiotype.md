---
UID: NF.wdfdevice.WdfDeviceInitSetIoType
title: WdfDeviceInitSetIoType function
author: windows-driver-content
description: The WdfDeviceInitSetIoType method sets the method or preference for how a driver will access the data buffers that are included in read and write requests for a specified device.
old-location: wdf\wdfdeviceinitsetiotype.htm
old-project: wdf
ms.assetid: fcad4b8e-4273-43ff-8077-a96d1bd4640a
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfDeviceInitSetIoType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDeviceInitSetIoType
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: ChildDeviceInitAPI, ControlDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfDeviceInitSetIoType function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceInitSetIoType</b> method sets the method or preference for how a driver will access the data buffers that are included in read and write requests for a specified device.



## -syntax

````
void WdfDeviceInitSetIoType(
  _In_ PWDFDEVICE_INIT    DeviceInit,
  _In_ WDF_DEVICE_IO_TYPE IoType
);
````


## -parameters

### -param DeviceInit [in]

A pointer to a <a href="wdf.wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param IoType [in]

A <a href="wdf.wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>-typed enumerator that identifies the method that the driver will use to access data buffers that it receives for read and write requests.


## -returns
This method does not return a value.


## -remarks
<b>KMDF </b>If you are writing a new driver using KMDF version 1.13 or later, you should instead use <a href="wdf.wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>. Calling <b>WdfDeviceInitSetIoType</b> from a KMDF filter driver has no effect. For filter drivers, the framework uses the I/O type specified by the next-lower driver in the driver stack.

<b>UMDF </b>If you are converting a KMDF driver that calls <b>WdfDeviceInitSetIoType</b> to UMDF version 2.0 or later, your converted driver can continue to call <b>WdfDeviceInitSetIoType</b> without issue. However, if you are writing an entirely  new driver using UMDF version 2.0 or later, you should instead use <a href="wdf.wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>.

If a driver calls <b>WdfDeviceInitSetIoType</b>, it must do so before it calls <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="wdf.creating_a_framework_device_object">Creating a Framework Device Object</a>.

If the driver does not call <b>WdfDeviceInitSetIoType</b>, the framework sets the driver's buffer-access method to <b>WdfDeviceIoBuffered</b>, for the specified device.

For more information about buffer-access methods, see <a href="wdf.accessing_data_buffers_in_kmdf_drivers">Accessing Data Buffers</a>.

The following code example indicates that a driver will use the direct I/O method when it accesses the device.


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
Minimum KMDF version

</th>
<td width="70%">
1.0

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
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_childdeviceinitapi">ChildDeviceInitAPI</a>, <a href="devtest.kmdf_controldeviceinitapi">ControlDeviceInitAPI</a>, <a href="devtest.kmdf_deviceinitapi">DeviceInitAPI</a>, <a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_pdodeviceinitapi">PdoDeviceInitAPI</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.iwdfdeviceinitialize2_setiotypepreference"> IWDFDeviceInitialize2::SetIoTypePreference</a>
</dt>
<dt>
<a href="wdf.wdf_device_io_type">WDF_DEVICE_IO_TYPE</a>
</dt>
<dt>
<a href="wdf.wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetIoType method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

