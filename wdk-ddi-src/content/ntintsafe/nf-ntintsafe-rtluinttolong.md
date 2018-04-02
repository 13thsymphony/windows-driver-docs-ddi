---
UID: NF:ntintsafe.RtlUIntToLong
title: RtlUIntToLong function
author: windows-driver-content
description: Converts a value of type UINT to a value of type LONG.
old-location: kernel\rtluinttolong.htm
old-project: kernel
ms.assetid: 9C388D02-003B-4B0E-B2ED-E311AE750601
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUIntToLong, RtlUIntToLong function [Kernel-Mode Driver Architecture], kernel.rtluinttolong, ntintsafe/RtlUIntToLong
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
-	RtlUIntToLong
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntToLong function
Converts a value of type <b>UINT</b> to a value of type <b>LONG</b>.

## Syntax

```
NTSTATUS RtlUIntToLong(
  UINT uOperand,
  LONG *plResult
);
```

## Parameters

`uOperand`

The value to be converted.

`plResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntToLongPtr
</li>
<li>RtlUInt32ToLong
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |