---
UID: NF:ntintsafe.RtlUShortToUInt8
title: RtlUShortToUInt8 function
author: windows-driver-content
description: Converts a value of type USHORT to a value of type UINT8.
old-location: kernel\rtlushorttouint8.htm
old-project: kernel
ms.assetid: 79D98E31-96A2-477B-83AE-C5EB419D482B
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUShortToUInt8, RtlUShortToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtlushorttouint8, ntintsafe/RtlUShortToUInt8
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
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
-	Ntintsafe.h
api_name:
-	RtlUShortToUInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUShortToUInt8 function
Converts a value of type <b>USHORT</b> to a value of type <b>UINT8</b>.

## Syntax

```
NTSTATUS RtlUShortToUInt8(
  USHORT usOperand,
  UINT8  *pui8Result
);
```

## Parameters

`usOperand`

The value to be converted.

`pui8Result`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |