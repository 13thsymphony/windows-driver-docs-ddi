---
UID: NF:ntintsafe.RtlInt8ToUInt
title: RtlInt8ToUInt function
author: windows-driver-content
description: Converts a value of type INT8 to a value of type UINT.
old-location: kernel\rtlint8touint.htm
old-project: kernel
ms.assetid: 00C37CB5-4CBC-48C3-8D90-F01BF82E2EF6
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlInt8ToUInt, RtlInt8ToUInt function [Kernel-Mode Driver Architecture], kernel.rtlint8touint, ntintsafe/RtlInt8ToUInt
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
-	RtlInt8ToUInt
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlInt8ToUInt function
Converts a value of type <b>INT8</b> to a value of type <b>UINT</b>.

## Syntax

```
NTSTATUS RtlInt8ToUInt(
  INT8 i8Operand,
  UINT *puResult
);
```

## Parameters

`i8Operand`

The value to be converted.

`puResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlInt8ToUInt32
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |