---
UID: NF:ntintsafe.RtlUIntPtrToInt8
title: RtlUIntPtrToInt8 function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type INT8.
old-location: kernel\rtluintptrtoint8.htm
old-project: kernel
ms.assetid: BA484BB1-550E-48F1-A400-86F62D59A0A1
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUIntPtrToInt8, RtlUIntPtrToInt8 function [Kernel-Mode Driver Architecture], kernel.rtluintptrtoint8, ntintsafe/RtlUIntPtrToInt8
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
-	RtlUIntPtrToInt8
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntPtrToInt8 function
Converts a value of type <b>UINT_PTR</b> to a value of type <b>INT8</b>.

## Syntax

```
NTSTATUS RtlUIntPtrToInt8(
  UINT_PTR uOperand,
  INT8     *pi8Result
);
```

## Parameters

`uOperand`

The value to be converted.

`pi8Result`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlSizeTToInt8
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |