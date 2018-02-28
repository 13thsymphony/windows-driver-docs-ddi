---
UID: NF:ntintsafe.RtlULongToShort
title: RtlULongToShort function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type SHORT.
old-location: kernel\rtlulongtoshort.htm
old-project: kernel
ms.assetid: CF44513A-8BFE-453F-A3C1-BF50C86A663E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlULongToShort, RtlULongToShort function [Kernel-Mode Driver Architecture], kernel.rtlulongtoshort, ntintsafe/RtlULongToShort
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
-	RtlULongToShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongToShort function
Converts a value of type <b>ULONG</b> to a value of type <b>SHORT</b>.

## Syntax

````
NTSTATUS RtlULongToShort(
  _In_  ULONG ulOperand,
  _Out_ SHORT *psResult
);
````

## Parameters

`ulOperand`

The value to be converted.

`psResult`

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