---
UID : NF:ks.KsDefaultDeviceIoCompletion
title : KsDefaultDeviceIoCompletion function
author : windows-driver-content
description : The KsDefaultDeviceIoCompletion function is used to return a default response and to complete any device I/O control.
old-location : stream\ksdefaultdeviceiocompletion.htm
old-project : stream
ms.assetid : 6e466815-aef4-4602-b3cf-66b47b2e3f3b
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsDefaultDeviceIoCompletion
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
req.alt-api : KsDefaultDeviceIoCompletion
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


# KsDefaultDeviceIoCompletion function
The <b>KsDefaultDeviceIoCompletion</b> function is used to return a default response and to complete any device I/O control. It can be used in the KSDISPATCH_TABLE and as the default response to unknown Ioctl's. It is important to use this function so that queries such as property requests return the correct value rather than just STATUS_INVALID_DEVICE_REQUEST when properties are not support for instance.

## Syntax

````
NTSTATUS KsDefaultDeviceIoCompletion(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PIRP           Irp
);
````

## Parameters

`DeviceObject`

Specifies the device object dispatched to.

`Irp`

Specifies the IRP to return a default response to.


## Return Value

The <b>KsDefaultDeviceIoCompletion</b> function returns the default response to the possible IOCTLs.

## Remarks

Note that this routine will complete the IRP.</p>

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