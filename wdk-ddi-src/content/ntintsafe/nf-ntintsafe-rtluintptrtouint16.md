---
UID: NF:ntintsafe.RtlUIntPtrToUInt16
title: RtlUIntPtrToUInt16 function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type UINT16.
old-location: kernel\rtluintptrtouint16.htm
old-project: kernel
ms.assetid: 405FB676-64FD-43DE-BCD9-233C8B43D851
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUIntPtrToUInt16, RtlUIntPtrToUInt16 function [Kernel-Mode Driver Architecture], kernel.rtluintptrtouint16, ntintsafe/RtlUIntPtrToUInt16
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
-	RtlUIntPtrToUInt16
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntPtrToUInt16 function
Converts a value of type <b>UINT_PTR</b> to a value of type <b>UINT16</b>.

## Syntax

```
NTSTATUS RtlUIntPtrToUInt16(
  UINT_PTR uOperand,
  UINT16   *pu16Result
);
```

## Parameters

`uOperand`

The value to be converted.

`pu16Result`

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