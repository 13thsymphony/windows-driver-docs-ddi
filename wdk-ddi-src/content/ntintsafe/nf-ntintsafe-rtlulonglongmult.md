---
UID: NF:ntintsafe.RtlULongLongMult
title: RtlULongLongMult function
author: windows-driver-content
description: Multiplies one value of type ULONGLONG by another.
old-location: kernel\rtlulonglongmult.htm
old-project: kernel
ms.assetid: 9865C8D1-DA20-4733-8862-7CA38069A93F
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlULongLongMult, RtlULongLongMult function [Kernel-Mode Driver Architecture], kernel.rtlulonglongmult, ntintsafe/RtlULongLongMult
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
-	RtlULongLongMult
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongLongMult function
Multiplies one value of type <b>ULONGLONG</b> by another.

## Syntax

```
NTSTATUS RtlULongLongMult(
  ULONGLONG ullMultiplicand,
  ULONGLONG ullMultiplier,
  ULONGLONG *pullResult
);
```

## Parameters

`ullMultiplicand`

The value to be multiplied by <i>ullMultiplier</i>.

`ullMultiplier`

The value by which to multiply <i>ullMultiplicand</i>.

`pullResult`

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |