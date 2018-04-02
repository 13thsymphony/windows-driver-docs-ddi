---
UID: NF:ntintsafe.RtlShortToUInt8
title: RtlShortToUInt8 function
author: windows-driver-content
description: Converts a value of type SHORT to a value of type UINT8.
old-location: kernel\rtlshorttouint8.htm
old-project: kernel
ms.assetid: B1B5AE37-23BC-444A-9014-529BAD50ED52
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlShortToUInt8, RtlShortToUInt8 function [Kernel-Mode Driver Architecture], kernel.rtlshorttouint8, ntintsafe/RtlShortToUInt8
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
-	RtlShortToUInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlShortToUInt8 function
Converts a value of type <b>SHORT</b> to a value of type <b>UINT8</b>.

## Syntax

```
NTSTATUS RtlShortToUInt8(
  SHORT sOperand,
  UINT8 *pui8Result
);
```

## Parameters

`sOperand`

The value to be converted.

`pui8Result`

TBD


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlShortToByte
</li>
<li>RtlInt16ToUInt8
</li>
<li>RtlInt16ToByte
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |