---
UID: NF:ntintsafe.RtlULongToInt8
title: RtlULongToInt8 function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type INT8.
old-location: kernel\rtlulongtoint8.htm
old-project: kernel
ms.assetid: E44C756E-BD9B-4DC0-9F6D-07A366ED72B7
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlULongToInt8, RtlULongToInt8 function [Kernel-Mode Driver Architecture], kernel.rtlulongtoint8, ntintsafe/RtlULongToInt8
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
-	RtlULongToInt8
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongToInt8 function
Converts a value of type <b>ULONG</b> to a value of type <b>INT8</b>.

## Syntax

```
NTSTATUS RtlULongToInt8(
  ULONG ulOperand,
  INT8  *pi8Result
);
```

## Parameters

`ulOperand`

The value to be converted.

`pi8Result`

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