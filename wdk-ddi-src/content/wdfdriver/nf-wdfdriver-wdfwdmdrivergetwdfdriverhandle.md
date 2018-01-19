---
UID : NF:wdfdriver.WdfWdmDriverGetWdfDriverHandle
title : WdfWdmDriverGetWdfDriverHandle function
author : windows-driver-content
description : The WdfWdmDriverGetWdfDriverHandle method returns a handle to the framework driver object that is associated with a specified Windows Driver Model (WDM) driver object.
old-location : wdf\wdfwdmdrivergetwdfdriverhandle.htm
old-project : wdf
ms.assetid : 2126d36c-42c1-4e29-bf82-9f5682482557
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : WdfWdmDriverGetWdfDriverHandle
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfdriver.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 
req.alt-api : WdfWdmDriverGetWdfDriverHandle
req.alt-loc : Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance : DriverCreate
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (see Framework Library Versioning.)
req.dll : 
req.irql : Any level
req.typenames : WDF_DRIVER_INIT_FLAGS
req.product : Windows 10 or later.
---


# WdfWdmDriverGetWdfDriverHandle function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfWdmDriverGetWdfDriverHandle</b> method returns a handle to the framework driver object that is associated with a specified Windows Driver Model (WDM) driver object.

## Syntax

````
WDFDRIVER WdfWdmDriverGetWdfDriverHandle(
  _In_ PDRIVER_OBJECT DriverObject
);
````

## Parameters

`DriverObject`

A pointer to a WDM driver object.


## Return Value

<b>WdfWdmDriverGetWdfDriverHandle</b> returns a handle to a framework driver object. A system bug check occurs if the <i>DriverObject</i> pointer is <b>NULL</b>. 

The following code example obtains a handle to the framework driver object that is associated with a specified WDM driver object.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** |  |
| **Header** | wdfdriver.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** | DriverCreate |