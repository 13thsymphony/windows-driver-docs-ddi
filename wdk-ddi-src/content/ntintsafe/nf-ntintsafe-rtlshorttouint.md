---
UID: NF:ntintsafe.RtlShortToUInt
title: RtlShortToUInt function
author: windows-driver-content
description: Converts a value of type SHORT to a value of type UINT.
old-location: kernel\rtlshorttouint.htm
old-project: kernel
ms.assetid: D4651C81-7171-4D54-BB76-EE822AABC1C3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntintsafe/RtlShortToUInt, kernel.rtlshorttouint, RtlShortToUInt, RtlShortToUInt function [Kernel-Mode Driver Architecture]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntintsafe.h
apiname:
-	RtlShortToUInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlShortToUInt function
Converts a value of type <b>SHORT</b> to a value of type <b>UINT</b>.

## Syntax

````
NTSTATUS RtlShortToUInt(
  _In_  SHORT sOperand,
  _Out_ UINT  *puResult
);
````

## Parameters

`sOperand`

The value to be converted.

`puResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlShortToUInt32
</li>
<li>RtlInt16ToUInt
</li>
<li>RtlInt16ToUInt32
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |