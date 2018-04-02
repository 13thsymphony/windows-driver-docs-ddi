---
UID: NF:ntintsafe.RtlULongPtrSub
title: RtlULongPtrSub function
author: windows-driver-content
description: Subtracts one value of type ULONG_PTR from another.
old-location: kernel\rtlulongptrsub.htm
old-project: kernel
ms.assetid: E8F9A1B0-5E87-4CB0-8C9E-5C2494F07C39
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlULongPtrSub, RtlULongPtrSub function [Kernel-Mode Driver Architecture], kernel.rtlulongptrsub, ntintsafe/RtlULongPtrSub
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
-	RtlULongPtrSub
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongPtrSub function
Subtracts one value of type <b>ULONG_PTR</b> from another.

## Syntax

```
NTSTATUS RtlULongPtrSub(
  ULONG_PTR ulMinuend,
  ULONG_PTR ulSubtrahend,
  ULONG_PTR *pulResult
);
```

## Parameters

`ulMinuend`

The value from which <i>ulSubtrahend</i> is subtracted.

`ulSubtrahend`

The value to subtract from <i>ulMinuend</i>.

`pulResult`

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