---
UID: NF:ntintsafe.RtlUIntMult
title: RtlUIntMult function
author: windows-driver-content
description: Multiplies one value of type UINT by another.
old-location: kernel\rtluintmult.htm
old-project: kernel
ms.assetid: 9972BC53-3CFB-4649-9C54-B194039D804F
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.rtluintmult, ntintsafe/RtlUIntMult, RtlUIntMult function [Kernel-Mode Driver Architecture], RtlUIntMult
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
-	RtlUIntMult
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntMult function
Multiplies one value of type <b>UINT</b> by another.

## Syntax

````
NTSTATUS RtlUIntMult(
  _In_  UINT uMultiplicand,
  _In_  UINT uMultiplier,
  _Out_ UINT *puResult
);
````

## Parameters

`uMultiplicand`

The value to be multiplied by <i>uMultiplier</i>.

`uMultiplier`

The value by which to multiply <i>uMultiplicand</i>.

`puResult`

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUInt32Mult
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |