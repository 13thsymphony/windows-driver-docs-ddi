---
UID: NF:ntintsafe.RtlULongToInt8
title: RtlULongToInt8 function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type INT8.
old-location: kernel\rtlulongtoint8.htm
old-project: kernel
ms.assetid: E44C756E-BD9B-4DC0-9F6D-07A366ED72B7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlulongtoint8, RtlULongToInt8, RtlULongToInt8 function [Kernel-Mode Driver Architecture], ntintsafe/RtlULongToInt8
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
-	RtlULongToInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongToInt8 function
Converts a value of type <b>ULONG</b> to a value of type <b>INT8</b>.

## Syntax

````
NTSTATUS RtlULongToInt8(
  _In_  ULONG ulOperand,
  _Out_ INT8  *pi8Result
);
````

## Parameters

`ulOperand`

The value to be converted.

`pi8Result`

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