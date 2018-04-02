---
UID: NF:ntintsafe.RtlULongPtrToLongLong
title: RtlULongPtrToLongLong function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type LONGLONG.
old-location: kernel\rtlulongptrtolonglong.htm
old-project: kernel
ms.assetid: 55DB2888-8427-4714-A72C-1F0C2804C3EA
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlULongPtrToLongLong, RtlULongPtrToLongLong function [Kernel-Mode Driver Architecture], kernel.rtlulongptrtolonglong, ntintsafe/RtlULongPtrToLongLong
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
-	RtlULongPtrToLongLong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongPtrToLongLong function
Converts a value of type <b>ULONG_PTR</b> to a value of type <b>LONGLONG</b>.

## Syntax

```
NTSTATUS RtlULongPtrToLongLong(
  ULONG_PTR ulOperand,
  LONGLONG  *pllResult
);
```

## Parameters

`ulOperand`

The value to be converted.

`pllResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlULongPtrToLong64
</li>
<li>RtlULongPtrToInt64
</li>
<li>RtlDWordPtrToLongLong
</li>
<li>RtlDWordPtrToLong64
</li>
<li>RtlDWordPtrToInt64
</li>
<li>RtlSIZETToLongLong
</li>
<li>RtlSIZETToLong64
</li>
<li>RtlSIZETToInt64
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |