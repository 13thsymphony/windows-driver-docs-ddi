---
UID: NC.ucxusbdevice.EVT_UCX_USBDEVICE_SUSPEND
title: EVT_UCX_USBDEVICE_SUSPEND
author: windows-driver-content
description: UCX invokes this callback function to send a device suspend state.
old-location: buses\evt_ucx_usbdevice_suspend.htm
old-project: UsbRef
ms.assetid: 809F946C-DDD4-4C4D-9F0F-F2B4A4657D12
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
req.alt-api: *PFN_UCX_USBDEVICE_SUSPEND
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
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# EVT_UCX_USBDEVICE_SUSPEND callback



## -description
UCX invokes this callback function to send a device suspend state.



## -prototype

````
EVT_UCX_USBDEVICE_SUSPEND EvtUcxDeviceSuspend;

void EvtUcxDeviceSuspend(
  _In_ UCXCONTROLLER UcxController,
  _In_ UCXUSBDEVICE  UcxUsbDevice
)
{ ... }

typedef EVT_UCX_USBDEVICE_SUSPEND *PFN_UCX_USBDEVICE_SUSPEND;
````


## -parameters

### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="buses._ucxcontrollercreate">UcxControllerCreate</a> method.


### -param UcxUsbDevice [in]

A handle to a UCX object that represents the USB device that the client driver received in a previous call to the <a href="buses._ucxusbdevicecreate">UcxUsbDeviceCreate</a> method.


## -returns
This callback function does not return a value.


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
PASSIVE_LEVEL

</td>
</tr>
</table>