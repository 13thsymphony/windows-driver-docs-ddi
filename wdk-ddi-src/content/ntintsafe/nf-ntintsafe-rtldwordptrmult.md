---
UID: NF:ntintsafe.RtlDWordPtrMult
title: RtlDWordPtrMult function
author: windows-driver-content
description: Multiplies one value of type DWORD_PTR by another.
old-location: kernel\rtldwordptrmult.htm
old-project: kernel
ms.assetid: E7EEE6D7-19C8-481F-BAEF-15998819D2D0
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlDWordPtrMult, RtlDWordPtrMult function [Kernel-Mode Driver Architecture], kernel.rtldwordptrmult, ntintsafe/RtlDWordPtrMult
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
-	RtlDWordPtrMult
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlDWordPtrMult function
Multiplies one value of type <b>DWORD_PTR</b> by another.

## Syntax

````
NTSTATUS RtlDWordPtrMult(
  _In_  DWORD_PTR dwMultiplicand,
  _In_  DWORD_PTR dwMultiplier,
  _Out_ DWORD_PTR *pdwResult
);
````

## Parameters

`dwMultiplicand`

The value to be multiplied by <i>dwMultiplier</i>.

`dwMultiplier`

The value by which to multiply <i>dwMultiplicand</i>.

`pdwResult`

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