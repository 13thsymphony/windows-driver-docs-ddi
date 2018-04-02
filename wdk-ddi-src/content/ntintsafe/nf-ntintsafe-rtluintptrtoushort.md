---
UID: NF:ntintsafe.RtlUIntPtrToUShort
title: RtlUIntPtrToUShort function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type USHORT.
old-location: kernel\rtluintptrtoushort.htm
old-project: kernel
ms.assetid: 7C65771B-B60E-459F-AB71-1091B45C5A1A
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUIntPtrToUShort, RtlUIntPtrToUShort function [Kernel-Mode Driver Architecture], kernel.rtluintptrtoushort, ntintsafe/RtlUIntPtrToUShort
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
-	RtlUIntPtrToUShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntPtrToUShort function
Converts a value of type <b>UINT_PTR</b> to a value of type <b>USHORT</b>.

## Syntax

```
NTSTATUS RtlUIntPtrToUShort(
  UINT_PTR uOperand,
  USHORT   *pusResult
);
```

## Parameters

`uOperand`

The value to be converted.

`pusResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrToWord
</li>
<li>RtlSizeTToUShort
</li>
<li>RtlSizeTToUInt16
</li>
<li>RtlSizeTToWord
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |