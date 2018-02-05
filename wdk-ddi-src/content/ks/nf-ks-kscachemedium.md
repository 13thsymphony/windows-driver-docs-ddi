---
UID : NF:ks.KsCacheMedium
title : KsCacheMedium function
author : windows-driver-content
description : The KsCacheMedium function improves graph building performance of pins that use Mediums to define connectivity.
old-location : stream\kscachemedium.htm
old-project : stream
ms.assetid : d0e9c146-5d73-49e8-92a8-c453f5bbbfe9
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ks/KsCacheMedium, KsCacheMedium function [Streaming Media Devices], ksfunc_19ac113f-3eb8-4073-90b0-786cc82cdf37.xml, stream.kscachemedium, KsCacheMedium
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---


# KsCacheMedium function
The <b>KsCacheMedium</b> function improves graph building performance of pins that use Mediums to define connectivity.

## Syntax

````
NTSTATUS KsCacheMedium(
  _In_ PUNICODE_STRING SymbolicLink,
  _In_ PKSPIN_MEDIUM   Medium,
  _In_ ULONG           PinDirection
);
````

## Parameters

`SymbolicLink`

The symbolic link used to open the device interface.

`Medium`

Points to the medium to cache.

`PinDirection`

Contains the direction of the Pin.  1 is output, 0 is input.


## Return Value

<b>KsCacheMedium</b> returns STATUS_SUCCESS if the caching operation is successful, failure if it is not.

## Remarks

<b>KsCacheMedium</b> improves graph building performance by creating a registry key at: 

<b>\System\CurrentControlSet\Control\MediumCache\GUID\DWORD\DWORD </b>

This enables fast lookup of connected filters in TvTuner and other complex graphs.  Note that the GUID identifies the Medium of the connection, and that the DWORDs denote the device instance.  The value name is the SymbolicLink for the driver, and ActualValue is the pin direction.turning.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ks.h (include Ks.h) |
| **Library** | Ks.lib |