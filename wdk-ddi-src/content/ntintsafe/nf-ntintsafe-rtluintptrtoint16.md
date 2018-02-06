---
UID: NF:ntintsafe.RtlUIntPtrToInt16
title: RtlUIntPtrToInt16 function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type INT16.
old-location: kernel\rtluintptrtoint16.htm
old-project: kernel
ms.assetid: 11FA2777-93AA-4833-8726-4C6E5FADD0B9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtluintptrtoint16, RtlUIntPtrToInt16, RtlUIntPtrToInt16 function [Kernel-Mode Driver Architecture], ntintsafe/RtlUIntPtrToInt16
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
-	RtlUIntPtrToInt16
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntPtrToInt16 function
Converts a value of type <b>UINT_PTR</b> to a value of type <b>INT16</b>.

## Syntax

````
NTSTATUS RtlUIntPtrToInt16(
  _In_  UINT_PTR uOperand,
  _Out_ INT16    *pi16Result
);
````

## Parameters

`uOperand`

The value to be converted.

`pi16Result`

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