---
UID: NF:ntintsafe.RtlInt8Add
title: RtlInt8Add function
author: windows-driver-content
description: Adds two values of type INT8.
old-location: kernel\rtlint8add.htm
old-project: kernel
ms.assetid: E97C3EA9-2244-458E-BE5E-6312023118A3
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlInt8Add, RtlInt8Add function [Kernel-Mode Driver Architecture], kernel.rtlint8add, ntintsafe/RtlInt8Add
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
-	RtlInt8Add
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlInt8Add function
Adds two values of type <b>INT8</b>.

## Syntax

```
NTSTATUS RtlInt8Add(
  INT8 i8Augend,
  INT8 i8Addend,
  INT8 *pi8Result
);
```

## Parameters

`i8Augend`

The first value in the equation.

`i8Addend`

The value to add to <i>i8Augend</i>.

`pi8Result`

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |