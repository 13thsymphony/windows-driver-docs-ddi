---
UID: NF:ntintsafe.RtlUIntSub
title: RtlUIntSub function
author: windows-driver-content
description: Subtracts one value of type UINT from another.
old-location: kernel\rtluintsub.htm
old-project: kernel
ms.assetid: 0886578A-C1CF-4A48-86A3-407A0C16ADEC
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlUIntSub, RtlUIntSub function [Kernel-Mode Driver Architecture], kernel.rtluintsub, ntintsafe/RtlUIntSub
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
-	RtlUIntSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntSub function
Subtracts one value of type <b>UINT</b> from another.

## Syntax

```
NTSTATUS RtlUIntSub(
  UINT uMinuend,
  UINT uSubtrahend,
  UINT *puResult
);
```

## Parameters

`uMinuend`

The value from which <i>u8Subtrahend</i> is subtracted.

`uSubtrahend`

The value to subtract from <i>u8Minuend</i>.

`puResult`

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUInt32Sub
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |