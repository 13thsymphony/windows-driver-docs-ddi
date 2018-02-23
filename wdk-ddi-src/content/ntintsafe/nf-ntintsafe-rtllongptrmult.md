---
UID: NF:ntintsafe.RtlLongPtrMult
title: RtlLongPtrMult function
author: windows-driver-content
description: Multiplies one value of type LONG_PTR by another.
old-location: kernel\rtllongptrmult.htm
old-project: kernel
ms.assetid: AF602DBE-E106-4105-B56B-DE9EE7691A05
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlLongPtrMult, kernel.rtllongptrmult, RtlLongPtrMult function [Kernel-Mode Driver Architecture], ntintsafe/RtlLongPtrMult
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
-	RtlLongPtrMult
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlLongPtrMult function
Multiplies one value of type <b>LONG_PTR</b> by another.

## Syntax

````
NTSTATUS RtlLongPtrMult(
  _In_  LONG_PTR lMultiplicand,
  _In_  LONG_PTR lMultiplier,
  _Out_ LONG_PTR *plResult
);
````

## Parameters

`lMultiplicand`

The value to be multiplied by <i>lMultiplier</i>.

`lMultiplier`

The value by which to multiply <i>lMultiplicand</i>.

`plResult`

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