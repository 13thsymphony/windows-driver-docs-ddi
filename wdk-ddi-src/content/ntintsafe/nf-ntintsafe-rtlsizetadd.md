---
UID: NF:ntintsafe.RtlSizeTAdd
title: RtlSizeTAdd function
author: windows-driver-content
description: Adds two values of type SIZE_T.
old-location: kernel\rtlsizetadd.htm
old-project: kernel
ms.assetid: A3A2BD4D-F95D-4427-BE63-80A6E9AC9293
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlSizeTAdd, RtlSizeTAdd function [Kernel-Mode Driver Architecture], kernel.rtlsizetadd, ntintsafe/RtlSizeTAdd
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
-	RtlSizeTAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlSizeTAdd function
Adds two values of type <b>SIZE_T</b>.

## Syntax

```
NTSTATUS RtlSizeTAdd(
  size_t Augend,
  size_t Addend,
  size_t *pResult
);
```

## Parameters

`Augend`

The first value in the equation.

`Addend`

The value to add to <i>Augend</i>.

`pResult`

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