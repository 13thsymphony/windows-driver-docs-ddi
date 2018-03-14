---
UID: NF:ntintsafe.RtlIntPtrToLongPtr
title: RtlIntPtrToLongPtr function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type LONG_PTR.
old-location: kernel\rtlintptrtolongptr.htm
old-project: kernel
ms.assetid: B04AE198-6677-4975-BAA0-96C228EFB038
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlIntPtrToLongPtr, RtlIntPtrToLongPtr function [Kernel-Mode Driver Architecture], kernel.rtlintptrtolongptr, ntintsafe/RtlIntPtrToLongPtr
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
-	RtlIntPtrToLongPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlIntPtrToLongPtr function
Converts a value of type <b>INT_PTR</b> to a value of type <b>LONG_PTR</b>.

## Syntax

````
NTSTATUS RtlIntPtrToLongPtr(
  _In_  INT_PTR  iOperand,
  _Out_ LONG_PTR *plResult
);
````

## Parameters

`iOperand`

The value to be converted.

`plResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlPtrdiffTToLongPtr
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |