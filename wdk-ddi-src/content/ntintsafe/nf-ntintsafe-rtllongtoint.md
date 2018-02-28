---
UID: NF:ntintsafe.RtlLongToInt
title: RtlLongToInt function
author: windows-driver-content
description: Converts a value of type LONG to a value of type INT.
old-location: kernel\rtllongtoint.htm
old-project: kernel
ms.assetid: 9C35B77E-FFEC-42A0-9D2C-9E52E210C941
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlLongToInt, RtlLongToInt function [Kernel-Mode Driver Architecture], kernel.rtllongtoint, ntintsafe/RtlLongToInt
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
req.lib: NtosKrnl.exe
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
-	RtlLongToInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlLongToInt function
Converts a value of type <b>LONG</b> to a value of type <b>INT</b>.

## Syntax

````
NTSTATUS RtlLongToInt(
  _In_  LONG lOperand,
  _Out_ INT  *piResult
);
````

## Parameters

`lOperand`

The value to be converted.

`piResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToInt32
</li>
<li>RtlLongToIntPtr
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |