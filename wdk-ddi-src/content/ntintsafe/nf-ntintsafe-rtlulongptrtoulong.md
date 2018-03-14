---
UID: NF:ntintsafe.RtlULongPtrToULong
title: RtlULongPtrToULong function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type ULONG.
old-location: kernel\rtlulongptrtoulong.htm
old-project: kernel
ms.assetid: 63F09DAA-C885-4A84-B0FF-249D8D6CA48C
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlULongPtrToULong, RtlULongPtrToULong function [Kernel-Mode Driver Architecture], kernel.rtlulongptrtoulong, ntintsafe/RtlULongPtrToULong
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
req.lib: 
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
-	RtlULongPtrToULong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongPtrToULong function
Converts a value of type <b>ULONG_PTR</b> to a value of type <b>ULONG</b>.

## Syntax

````
NTSTATUS RtlULongPtrToULong(
  _In_  ULONG_PTR ulOperand,
  _Out_ ULONG     *pulResult
);
````

## Parameters

`ulOperand`

The value to be converted.

`pulResult`

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