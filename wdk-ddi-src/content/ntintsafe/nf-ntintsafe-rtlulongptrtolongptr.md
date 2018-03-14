---
UID: NF:ntintsafe.RtlULongPtrToLongPtr
title: RtlULongPtrToLongPtr function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type LONG_PTR.
old-location: kernel\rtlulongptrtolongptr.htm
old-project: kernel
ms.assetid: 5231A8BC-2F7A-4A2C-931C-D3A81563754A
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlULongPtrToLongPtr, RtlULongPtrToLongPtr function [Kernel-Mode Driver Architecture], kernel.rtlulongptrtolongptr, ntintsafe/RtlULongPtrToLongPtr
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
-	RtlULongPtrToLongPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongPtrToLongPtr function
Converts a value of type <b>ULONG_PTR</b> to a value of type <b>LONG_PTR</b>.

## Syntax

````
NTSTATUS RtlULongPtrToLongPtr(
  _In_  ULONG_PTR ulOperand,
  _Out_ LONG_PTR  *plResult
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