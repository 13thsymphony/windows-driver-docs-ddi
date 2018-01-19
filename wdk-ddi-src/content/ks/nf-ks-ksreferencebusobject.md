---
UID : NF:ks.KsReferenceBusObject
title : KsReferenceBusObject function
author : windows-driver-content
description : References the bus Physical device object.
old-location : stream\ksreferencebusobject.htm
old-project : stream
ms.assetid : 96297c0a-a3ba-4f16-befb-ee6a55d2fb25
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsReferenceBusObject
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsReferenceBusObject
req.alt-loc : Ks.lib,Ks.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ks.lib
req.dll : 
req.irql : 
req.typenames : 
---


# KsReferenceBusObject function
References the bus Physical device object.

## Syntax

````
NTSTATUS KsReferenceBusObject(
  _In_ KSDEVICE_HEADER Header
);
````

## Parameters

`Header`

Points to a header previously allocated by <b>KsAllocateDeviceHeader</b> that also contains the PnP device stack object.


## Return Value

Returns STATUS_SUCCESS if the reference was successful, else an error such as STATUS_INSUFFICIENT_RESOURCES.

## Remarks

This function is used by filters that use the device header to keep track of their PnP object stack. This is normally called on a successful Open of the filter when the bus for this device requires such a reference (such as software devices), and is matched by a call to <a href="..\ks\nf-ks-ksdereferencebusobject.md">KsDereferenceBusObject</a> on a close of that filter instance. The caller must have previously also called KsSetDevicePnpAndBaseObject in order to set the PnP device stack object. This would have been done in the PnP AddDevice function. If the object has not been previously referenced, interface space is allocated and the function uses the PnP device object to acquire the bus referencing interface. It then calls the ReferenceDeviceObject method on that interface. The interface itself is released and freed when the device header is freed.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |