---
UID: NF:swenum.KsGetBusEnumPnpDeviceObject
title: KsGetBusEnumPnpDeviceObject function
author: windows-driver-content
description: The KsGetBusEnumPnpDeviceObject function retrieves the Plug and Play device object attached to the given device object.
old-location: stream\ksgetbusenumpnpdeviceobject.htm
old-project: stream
ms.assetid: 8e81a294-9388-467d-8405-472fbe9fe827
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: swenum/KsGetBusEnumPnpDeviceObject, stream.ksgetbusenumpnpdeviceobject, ksfunc_246a7c6e-ef5a-4cf4-a05a-70a499a487cb.xml, KsGetBusEnumPnpDeviceObject, KsGetBusEnumPnpDeviceObject function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: swenum.h
req.include-header: Swenum.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsGetBusEnumPnpDeviceObject
product: Windows
targetos: Windows
req.typenames: "*PSTREAM_TIME_REFERENCE, STREAM_TIME_REFERENCE"
req.product: Windows 10 or later.
---


# KsGetBusEnumPnpDeviceObject function
<i>This function is intended for internal use only.</i>

The <b>KsGetBusEnumPnpDeviceObject</b> function retrieves the Plug and Play device object attached to the given device object.

## Syntax

````
NTSTATUS KsGetBusEnumPnpDeviceObject(
  _In_  PDEVICE_OBJECT DeviceObject,
  _Out_ PDEVICE_OBJECT *PnpDeviceObject
);
````

## Parameters

`DeviceObject`

Pointer to the device object from which to retrieve the Plug and Play device object.

`PnpDeviceObject`

Pointer to the device object to receive the Plug and Play device object pointer.


## Return Value

Returns STATUS_SUCCESS if successful, or STATUS_INVALID_PARAMETER if <i>DeviceObject</i> does not contain a device extension, or if the device extension specified in <i>DeviceObject </i>is not that of an FDO.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | swenum.h (include Swenum.h) |
| **Library** | Ks.lib |