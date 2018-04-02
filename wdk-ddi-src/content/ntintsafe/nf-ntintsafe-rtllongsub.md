---
UID: NF:ntintsafe.RtlLongSub
title: RtlLongSub function
author: windows-driver-content
description: Subtracts one value of type LONG from another.
old-location: kernel\rtllongsub.htm
old-project: kernel
ms.assetid: 5D98737C-0986-4DCB-9270-A0DF76CFCB5C
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlLongSub, RtlLongSub function [Kernel-Mode Driver Architecture], kernel.rtllongsub, ntintsafe/RtlLongSub
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
-	RtlLongSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlLongSub function
Subtracts one value of type <b>LONG</b> from another.

## Syntax

```
NTSTATUS RtlLongSub(
  LONG lMinuend,
  LONG lSubtrahend,
  LONG *plResult
);
```

## Parameters

`lMinuend`

The value from which <i>lSubtrahend</i> is subtracted.

`lSubtrahend`

The value to subtract from <i>lMinuend</i>.

`plResult`

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