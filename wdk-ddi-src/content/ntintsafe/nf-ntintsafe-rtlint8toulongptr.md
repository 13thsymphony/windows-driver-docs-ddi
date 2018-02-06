---
UID: NF:ntintsafe.RtlInt8ToULongPtr
title: RtlInt8ToULongPtr function
author: windows-driver-content
description: Converts a value of type INT8 to a value of type ULONG_PTR.
old-location: kernel\rtlint8toulongptr.htm
old-project: kernel
ms.assetid: C406C404-1A6D-4D83-9D71-BC2980C1A84D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlInt8ToULongPtr function [Kernel-Mode Driver Architecture], kernel.rtlint8toulongptr, RtlInt8ToULongPtr, ntintsafe/RtlInt8ToULongPtr
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
-	RtlInt8ToULongPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlInt8ToULongPtr function
Converts a value of type <b>INT8</b> to a value of type <b>ULONG_PTR</b>.

## Syntax

````
NTSTATUS RtlInt8ToULongPtr(
  _In_  INT8      i8Operand,
  _Out_ ULONG_PTR *pulResult
);
````

## Parameters

`i8Operand`

The value to be converted.

`pulResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlInt8ToDWordPtr</li>
<li>RtlInt8ToSIZET
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |