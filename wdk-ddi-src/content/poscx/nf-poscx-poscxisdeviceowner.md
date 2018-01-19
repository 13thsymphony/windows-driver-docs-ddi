---
UID : NF:poscx.PosCxIsDeviceOwner
title : PosCxIsDeviceOwner function
author : windows-driver-content
description : PosCxIsDeviceOwner checks if the caller currently owns the claim on the device.
old-location : pos\poscxisdeviceowner.htm
old-project : pos
ms.assetid : 48D30A9D-3BA2-4929-865A-D9A34DC6E497
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PosCxIsDeviceOwner
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : poscx.h
req.include-header : Poscx.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PosCxIsDeviceOwner
req.alt-loc : poscx.h
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
req.typenames : POS_CX_EVENT_PRIORITY
req.product : Windows 10 or later.
---


# PosCxIsDeviceOwner function
PosCxIsDeviceOwner checks if the caller currently owns the claim on the device.

## Syntax

````
BOOLEAN PosCxIsDeviceOwner(
  _In_ WDFDEVICE     device,
  _In_ WDFFILEOBJECT fileObject
);
````

## Parameters

`device`

A handle to a framework device object that represents the device.

`fileObject`

A handle to a framework file object that identifies the caller, usually acquired with <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetfileobject.md">WdfRequestGetFileObject</a>. If this parameter is NULL, <b>PosCxIsDeviceOwner</b> returns TRUE if the device is not currently owned.


## Return Value

Returns TRUE if the caller is the device owner, or if <i>fileObject</i> is NULL and the device is not currently owned.

Otherwise, returns FALSE.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | poscx.h (include Poscx.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |