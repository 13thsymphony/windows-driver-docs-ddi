---
UID: NF:ntintsafe.RtlIntPtrToLong
title: RtlIntPtrToLong function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type LONG.
old-location: kernel\rtlintptrtolong.htm
old-project: kernel
ms.assetid: 408F7F44-9AA0-42C3-B7A0-0CFCDEAFAEAC
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlIntPtrToLong, RtlIntPtrToLong function [Kernel-Mode Driver Architecture], kernel.rtlintptrtolong, ntintsafe/RtlIntPtrToLong
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
-	RtlIntPtrToLong
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlIntPtrToLong function
Converts a value of type <b>INT_PTR</b> to a value of type <b>LONG</b>.

## Syntax

```
NTSTATUS RtlIntPtrToLong(
  INT_PTR iOperand,
  LONG    *plResult
);
```

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
<li>RtlPtrdiffTToLong
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |