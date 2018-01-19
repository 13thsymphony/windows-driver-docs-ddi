---
UID : NF:upssvc.UPSTurnOff
title : UPSTurnOff function
author : windows-driver-content
description : The UPSTurnOff function turns off the UPS unit's power outlets, after a specified delay time.
old-location : battery\upsturnoff.htm
old-project : battery
ms.assetid : 17ae946a-e57e-48bd-9213-cf47db2cba64
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : UPSTurnOff
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : upssvc.h
req.include-header : Upssvc.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : UPSTurnOff
req.alt-loc : upssvc.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : UMDETW_ALLOCATION_USAGE
req.product : Windows 10 or later.
---


# UPSTurnOff function
The <b>UPSTurnOff</b> function turns off the UPS unit's power outlets, after a specified delay time.

## Syntax

````
void UPSTurnOff(
  _In_ DWORD aTurnOffDelay
);
````

## Parameters

`aTurnOffDelay`

Specifies the minimum amount of time, in seconds, to wait before turning off the UPS unit's power outlets.


## Return Value

None

## Remarks

The actual delay time should not be less than that specified by <i>aTurnOffDelay</i>, to ensure adequate time for the operating system to shut down. 

The default value for <i>aTurnOffDelay </i>is 180 seconds.

The function must not postpone the request to turn off the power. Doing so could result in the operating system unloading the UPS service and the UPS minidriver.

On the other hand, the function must not turn off power from a UPS system that does not have an internal turnoff delay. Doing so will result in a premature loss of power to the computer, which can cause system corruption.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | upssvc.h (include Upssvc.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |