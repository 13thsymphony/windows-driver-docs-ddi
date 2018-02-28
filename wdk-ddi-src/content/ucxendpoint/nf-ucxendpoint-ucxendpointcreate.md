---
UID: NF:ucxendpoint.UcxEndpointCreate
title: UcxEndpointCreate function
author: windows-driver-content
description: Creates an endpoint on the specified USB device object.
old-location: buses\_ucxendpointcreate.htm
old-project: usbref
ms.assetid: 2BB3B2CE-FD15-4D28-BBDA-29C3BB523874
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcxEndpointCreate, UcxEndpointCreate method [Buses], buses._ucxendpointcreate, ucxendpoint/UcxEndpointCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ucxendpoint.h
api_name:
-	UcxEndpointCreate
product: Windows
targetos: Windows
req.typenames: UCX_ENDPOINT_CHARACTERISTIC_TYPE
req.product: Windows 10 or later.
---


# UcxEndpointCreate function
Creates an endpoint on the specified USB device object.

## Syntax

````
NTSTATUS UcxEndpointCreate(
  [in]           UCXUSBDEVICE           UsbDevice,
  [out]          PUCXENDPOINT_INIT      *EndpointInit,
  [in, optional] PWDF_OBJECT_ATTRIBUTES Attributes,
  [out]          UCXENDPOINT            *Endpoint
);
````

## Parameters

`UsbDevice`

A handle to the USB device object that contains the endpoint. The client driver retrieved the handle in a previous call to <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>.

`EndpointInit`

A pointer to a <b>UCXENDPOINT_INIT</b> structure that describes various configuration
        operations for creating the endpoint object. The driver specifies function pointers to its callback functions in this structure.
    This structure is managed by UCX.

`Attributes`

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies attributes for the endpoint object.

`Endpoint`

A pointer to a variable that receives a handle to the new endpoint object.


## Return Value

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.

## Remarks

The client driver for the host controller must call this method after the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> call. The parent of the new endpoint object is the USB device object. 

The method initializes the endpoint object with information such as the type of endpoint, pipe, transfer, and maximum transfers size.

For a code example, see <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoint_add.md">EVT_UCX_USBDEVICE_ENDPOINT_ADD</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10  |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxendpoint.h (include Ucxclass.h, Ucxendpoint.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |