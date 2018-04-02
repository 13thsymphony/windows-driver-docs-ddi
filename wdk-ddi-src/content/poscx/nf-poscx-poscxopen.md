---
UID: NF:poscx.PosCxOpen
title: PosCxOpen function
author: windows-driver-content
description: PosCxOpen is called to create an open PosCx library instance. This function initializes all resources it needs to manage a single open instance. It should be called from the driver's EVT_WDF_DEVICE_FILE_CREATE callback.
old-location: pos\poscxopen.htm
old-project: pos
ms.assetid: 6AB1BB0A-B350-44D7-B0D0-9A19FD6DEE19
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: PosCxOpen, PosCxOpen function, pos.poscxopen, poscx/PosCxOpen
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	poscx.h
api_name:
-	PosCxOpen
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---


# PosCxOpen function
PosCxOpen is called to create an open PosCx library instance. This function initializes all resources it needs to manage a single open instance. It should be called from the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540868">EVT_WDF_DEVICE_FILE_CREATE</a>   callback.

## Syntax

```
NTSTATUS PosCxOpen(
  WDFDEVICE     device,
  WDFFILEOBJECT fileObject,
  ULONG         deviceInterfaceTag
);
```

## Parameters

`device`

A handle to a framework device object that represents the device.

`fileObject`

A handle to a framework file object that identifies the caller associated with the open instance.

`deviceInterfaceTag`

An identifier used to specify the caller's device interface in a multi-function device.  For a single-interface device, this value should be 0.


## Return Value

An appropriate NTSTATUS error code that indicates the open instance completion status.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | poscx.h (include Poscx.h) |