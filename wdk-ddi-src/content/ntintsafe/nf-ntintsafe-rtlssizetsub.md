---
UID: NF:ntintsafe.RtlSSIZETSub
title: RtlSSIZETSub function
author: windows-driver-content
description: Subtracts one value of type SSIZE_T from another.
old-location: kernel\rtlssizetsub.htm
old-project: kernel
ms.assetid: 6EFDD7BF-B347-4E02-905E-01F0F155DB6F
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlSSIZETSub, kernel.rtlssizetsub, RtlSSIZETSub function [Kernel-Mode Driver Architecture], ntintsafe/RtlSSIZETSub
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
-	RtlSSIZETSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlSSIZETSub function
Subtracts one value of type <b>SSIZE_T</b> from another.

## Syntax

````
NTSTATUS RtlSSIZETSub(
  _In_  SSIZE_T Minuend,
  _In_  SSIZE_T Subtrahend,
  _Out_ SSIZE_T *pResult
);
````

## Parameters

`Minuend`

The value from which <i>Subtrahend</i> is subtracted.

`Subtrahend`

The value to subtract from <i>Minuend</i>.

`pResult`

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