---
UID: NF:ntintsafe.RtlULongLongMult
title: RtlULongLongMult function
author: windows-driver-content
description: Multiplies one value of type ULONGLONG by another.
old-location: kernel\rtlulonglongmult.htm
old-project: kernel
ms.assetid: 9865C8D1-DA20-4733-8862-7CA38069A93F
ms.author: windowsdriverdev
ms.date: 2/16/2018
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntintsafe.h
apiname:
-	RtlULongLongMult
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongLongMult function
Multiplies one value of type <b>ULONGLONG</b> by another.

## Syntax

````
NTSTATUS RtlULongLongMult(
  _In_  ULONGLONG ullMultiplicand,
  _In_  ULONGLONG ullMultiplier,
  _Out_ ULONGLONG *pullResult
);
````

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
| **Library** | NtosKrnl.exe |