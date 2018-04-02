---
UID: NF:ntintsafe.RtlIntPtrSub
title: RtlIntPtrSub function
author: windows-driver-content
description: Subtracts one value of type INT_PTR from another.
old-location: kernel\rtlintptrsub.htm
old-project: kernel
ms.assetid: 72352FD3-4855-4630-AF42-368FF3A6B2BB
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlIntPtrSub, RtlIntPtrSub function [Kernel-Mode Driver Architecture], kernel.rtlintptrsub, ntintsafe/RtlIntPtrSub
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
-	RtlIntPtrSub
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlIntPtrSub function
Subtracts one value of type <b>INT_PTR</b> from another.

## Syntax

```
NTSTATUS RtlIntPtrSub(
  INT_PTR iMinuend,
  INT_PTR iSubtrahend,
  INT_PTR *piResult
);
```

## Parameters

`iMinuend`

The value from which <i>iSubtrahend</i> is subtracted.

`iSubtrahend`

The value to subtract from <i>iMinuend</i>.

`piResult`

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |