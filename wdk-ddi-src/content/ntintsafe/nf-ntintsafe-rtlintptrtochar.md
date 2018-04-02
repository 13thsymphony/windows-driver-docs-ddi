---
UID: NF:ntintsafe.RtlIntPtrToChar
title: RtlIntPtrToChar function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type CHAR.
old-location: kernel\rtlintptrtochar.htm
old-project: kernel
ms.assetid: 96FC52D7-E383-451A-BB30-9C677F254DE2
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlIntPtrToChar, RtlIntPtrToChar function [Kernel-Mode Driver Architecture], kernel.rtlintptrtochar, ntintsafe/RtlIntPtrToChar
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
-	RtlIntPtrToChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlIntPtrToChar function
Converts a value of type <b>INT_PTR</b> to a value of type <b>CHAR</b>.

## Syntax

```
NTSTATUS RtlIntPtrToChar(
  INT_PTR iOperand,
  CHAR    *pch
);
```

## Parameters

`iOperand`

The value to be converted.

`pch`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlPtrdiffTToChar
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |