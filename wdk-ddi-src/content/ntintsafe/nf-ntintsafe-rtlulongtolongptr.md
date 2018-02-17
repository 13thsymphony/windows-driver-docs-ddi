---
UID: NF:ntintsafe.RtlULongToLongPtr
title: RtlULongToLongPtr function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type LONG_PTR.
old-location: kernel\rtlulongtolongptr.htm
old-project: kernel
ms.assetid: 707C2392-D78F-42E1-A9F8-9F502BF5227E
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlulongtolongptr, RtlULongToLongPtr function [Kernel-Mode Driver Architecture], RtlULongToLongPtr, ntintsafe/RtlULongToLongPtr
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
-	RtlULongToLongPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongToLongPtr function
Converts a value of type <b>ULONG</b> to a value of type <b>LONG_PTR</b>.

## Syntax

````
NTSTATUS RtlULongToLongPtr(
  _In_  ULONG    ulOperand,
  _Out_ LONG_PTR *plResult
);
````

## Parameters

`ulOperand`

The value to be converted.

`plResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |