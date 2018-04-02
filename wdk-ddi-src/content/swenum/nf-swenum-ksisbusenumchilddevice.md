---
UID: NF:swenum.KsIsBusEnumChildDevice
title: KsIsBusEnumChildDevice function
author: windows-driver-content
description: The KsIsBusEnumChildDevice function determines if the given device object is a child device of the demand-load bus enumerator object.
old-location: stream\ksisbusenumchilddevice.htm
old-project: stream
ms.assetid: 7b9aa600-dd47-4ef1-acc8-02fb1b4f51ce
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsIsBusEnumChildDevice, KsIsBusEnumChildDevice function [Streaming Media Devices], ksfunc_5718ba1d-d377-40f8-8972-7005f4064e7c.xml, stream.ksisbusenumchilddevice, swenum/KsIsBusEnumChildDevice
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsIsBusEnumChildDevice
product: Windows
targetos: Windows
req.typenames: STREAM_TIME_REFERENCE, *PSTREAM_TIME_REFERENCE
req.product: Windows 10 or later.
---


# KsIsBusEnumChildDevice function
<i>This function is intended for internal use only.</i>

The <b>KsIsBusEnumChildDevice</b> function determines if the given device object is a child device of the demand-load bus enumerator object.

## Syntax

```
KSDDKAPI NTSTATUS KsIsBusEnumChildDevice(
  PDEVICE_OBJECT DeviceObject,
  PBOOLEAN       ChildDevice
);
```

## Parameters

`DeviceObject`

Pointer to a device object.

`ChildDevice`

Pointer to a BOOLEAN to receive the result. <b>KsIsBusEnumChildDevice</b> sets this to <b>TRUE</b> if the given device object is a child device of the demand-load bus enumerator object, or <b>FALSE</b> otherwise.


## Return Value

Returns STATUS_SUCCESS if the given device object's device extension is valid; otherwise, it returns an error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | swenum.h (include Swenum.h) |
| **Library** | Ks.lib |