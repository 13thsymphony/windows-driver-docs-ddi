---
UID: NC.ucxusbdevice.EVT_UCX_USBDEVICE_GET_CHARACTERISTIC
title: EVT_UCX_USBDEVICE_GET_CHARACTERISTIC
author: windows-driver-content
description: UCX invokes this callback to retrieve the device characteristics.
old-location: buses\evt_ucx_usbdevice_get_characteristic.htm
old-project: UsbRef
ms.assetid: EE8568F6-3D88-477E-9F0D-044D014EBCF3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _STREAM_INFO, STREAM_INFO, *PSTREAM_INFO, PSTREAM_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: *PFN_UCX_USBDEVICE_GET_CHARACTERISTIC
req.alt-loc: ucxusbdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# EVT_UCX_USBDEVICE_GET_CHARACTERISTIC callback



## -description
 UCX invokes this callback to retrieve the device characteristics.



## -prototype

````
EVT_UCX_USBDEVICE_GET_CHARACTERISTIC EvtUcxDeviceGetCharacteristic;

NTSTATUS EvtUcxDeviceGetCharacteristic(
  _In_    UCXCONTROLLER                 UcxController,
  _In_    UCXUSBDEVICE                  UcxUsbDevice,
  _Inout_ PUCX_USBDEVICE_CHARACTERISTIC UcxUsbDeviceCharacteristic

)
{ ... }

typedef EVT_UCX_USBDEVICE_GET_CHARACTERISTIC *PFN_UCX_USBDEVICE_GET_CHARACTERISTIC;
````


## -parameters

### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="buses._ucxcontrollercreate">UcxControllerCreate</a> method.


### -param UcxUsbDevice [in]

A handle to a UCX object that represents the USB device that the client driver received in a previous call to the <a href="buses._ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.


### -param UcxUsbDeviceCharacteristic
</i> [in, out]
<dd>
A pointer to a <a href="buses.ucx_usbdevice_characteristic">UCX_USBDEVICE_CHARACTERISTIC</a> structure that contains the type of characteristic in which the caller is interested. The client driver fills the value of the requested  characteristic. For example, if the type indicates <a href="buses.ucx_usbdevice_characteristic_path_delay">UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY</a>, the driver fills the <b>UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY</b> structure, pointed to by <b>PathDelay</b> member, with the appropriate maximum and send path delay values.


## -returns
If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.


## -remarks
The UCX client driver registers its implementation with the USB host controller extension (UCX) by calling the <a href="buses._ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10, version 1709

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

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
<dt>Ucxusbdevice.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>