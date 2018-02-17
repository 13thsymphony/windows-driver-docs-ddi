---
UID: NF:ntintsafe.RtlSSIZETAdd
title: RtlSSIZETAdd function
author: windows-driver-content
description: Adds two values of type SSIZE_T.
old-location: kernel\rtlssizetadd.htm
old-project: kernel
ms.assetid: 1CBB3CDF-E7DD-4686-8EF6-FBCADE978A16
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlSSIZETAdd, ntintsafe/RtlSSIZETAdd, kernel.rtlssizetadd, RtlSSIZETAdd function [Kernel-Mode Driver Architecture]
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
-	RtlSSIZETAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlSSIZETAdd function
Adds two values of type <b>SSIZE_T</b>.

## Syntax

````
NTSTATUS RtlSSIZETAdd(
  _In_  SSIZE_T Augend,
  _In_  SSIZE_T Addend,
  _Out_ SSIZE_T *pResult
);
````

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
| **Library** | NtosKrnl.exe |