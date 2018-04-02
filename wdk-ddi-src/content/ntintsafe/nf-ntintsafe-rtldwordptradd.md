---
UID: NF:ntintsafe.RtlDWordPtrAdd
title: RtlDWordPtrAdd function
author: windows-driver-content
description: Adds two values of type DWORD_PTR.
old-location: kernel\rtldwordptradd.htm
old-project: kernel
ms.assetid: 8364FC5F-1FF4-415F-B83C-4A866C860522
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlDWordPtrAdd, RtlDWordPtrAdd function [Kernel-Mode Driver Architecture], kernel.rtldwordptradd, ntintsafe/RtlDWordPtrAdd
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
-	RtlDWordPtrAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlDWordPtrAdd function
Adds two values of type <b>DWORD_PTR</b>.

## Syntax

```
NTSTATUS RtlDWordPtrAdd(
  DWORD_PTR dwAugend,
  DWORD_PTR dwAddend,
  DWORD_PTR *pdwResult
);
```

## Parameters

`dwAugend`

The first value in the equation.

`dwAddend`

The value to add to <i>dwAugend</i>.

`pdwResult`

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