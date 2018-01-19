---
UID : NF:ks.KsFilterFactorySetDeviceClassesState
title : KsFilterFactorySetDeviceClassesState function
author : windows-driver-content
description : The KsFilterFactorySetDeviceClassesState function enables or disables the device classes that have been registered by a given filter factory.
old-location : stream\ksfilterfactorysetdeviceclassesstate.htm
old-project : stream
ms.assetid : 66515f08-b652-4aa0-8f22-b5ff0a407d6a
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KsFilterFactorySetDeviceClassesState
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ks.h
req.include-header : Ks.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KsFilterFactorySetDeviceClassesState
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
req.irql : PASSIVE_LEVEL
req.typenames : 
---


# KsFilterFactorySetDeviceClassesState function
The <b>KsFilterFactorySetDeviceClassesState</b> function enables or disables the device classes that have been registered by a given filter factory.

## Syntax

````
NTSTATUS KsFilterFactorySetDeviceClassesState(
  _In_ PKSFILTERFACTORY FilterFactory,
  _In_ BOOLEAN          NewState
);
````

## Parameters

`FilterFactory`

A pointer to the <a href="..\ks\ns-ks-_ksfilterfactory.md">KSFILTERFACTORY</a> for which to change device class status.

`NewState`

If set to <b>TRUE</b>, the device classes are enabled; if <b>FALSE</b>, they are disabled.


## Return Value

<b>KsFilterFactorySetDeviceClassesState</b> returns STATUS_SUCCESS or an error code.

## Remarks

This function is available in Windows XP and DirectX 8.0 and later.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h (include Ks.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |