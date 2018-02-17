---
UID: NF:ntintsafe.RtlShortToULong
title: RtlShortToULong function
author: windows-driver-content
description: Converts a value of type SHORT to a value of type ULONG.
old-location: kernel\rtlshorttoulong.htm
old-project: kernel
ms.assetid: A69F7F0E-3A71-4F29-9B56-A9B34D112F6C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlShortToULong, RtlShortToULong function [Kernel-Mode Driver Architecture], kernel.rtlshorttoulong, ntintsafe/RtlShortToULong
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
-	RtlShortToULong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlShortToULong function
Converts a value of type <b>SHORT</b> to a value of type <b>ULONG</b>.

## Syntax

````
NTSTATUS RtlShortToULong(
  _In_  SHORT sOperand,
  _Out_ ULONG *pulResult
);
````

## Parameters

`sOperand`

The value to be converted.

`pulResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlShortToDWord
</li>
<li>RtlInt16ToULong
</li>
<li>RtlInt16ToDWord
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |