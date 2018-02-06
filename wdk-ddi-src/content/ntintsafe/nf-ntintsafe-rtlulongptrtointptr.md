---
UID: NF:ntintsafe.RtlULongPtrToIntPtr
title: RtlULongPtrToIntPtr function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type INT_PTR.
old-location: kernel\rtlulongptrtointptr.htm
old-project: kernel
ms.assetid: 41687454-5468-4351-BEAF-2FB6BD80BEFC
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongPtrToIntPtr, RtlULongPtrToIntPtr function [Kernel-Mode Driver Architecture], ntintsafe/RtlULongPtrToIntPtr, kernel.rtlulongptrtointptr
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
-	RtlULongPtrToIntPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongPtrToIntPtr function
Converts a value of type <b>ULONG_PTR</b> to a value of type <b>INT_PTR</b>.

## Syntax

````
NTSTATUS RtlULongPtrToIntPtr(
  _In_  ULONG_PTR ulOperand,
  _Out_ INT_PTR   *piResult
);
````

## Parameters

`ulOperand`

The value to be converted.

`piResult`

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