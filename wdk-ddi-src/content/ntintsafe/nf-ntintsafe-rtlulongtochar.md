---
UID: NF:ntintsafe.RtlULongToChar
title: RtlULongToChar function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type CHAR.
old-location: kernel\rtlulongtochar.htm
old-project: kernel
ms.assetid: 43BD3798-0FCA-4A44-8EE1-DE252636CC95
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlULongToChar, RtlULongToChar function [Kernel-Mode Driver Architecture], kernel.rtlulongtochar, ntintsafe/RtlULongToChar
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntintsafe.h
api_name:
-	RtlULongToChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongToChar function
Converts a value of type <b>ULONG</b> to a value of type <b>CHAR</b>.

## Syntax

````
NTSTATUS RtlULongToChar(
  _In_  ULONG ulOperand,
  _Out_ CHAR  *pch
);
````

## Parameters

`ulOperand`

The value to be converted.

`pch`

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