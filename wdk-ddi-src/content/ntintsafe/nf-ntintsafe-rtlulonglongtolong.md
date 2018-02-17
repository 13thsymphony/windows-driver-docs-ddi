---
UID: NF:ntintsafe.RtlULongLongToLong
title: RtlULongLongToLong function
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type LONG.
old-location: kernel\rtlulonglongtolong.htm
old-project: kernel
ms.assetid: DC1784C6-0775-46E9-A439-B522713C297C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongLongToLong function [Kernel-Mode Driver Architecture], ntintsafe/RtlULongLongToLong, kernel.rtlulonglongtolong, RtlULongLongToLong
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
-	RtlULongLongToLong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongLongToLong function
Converts a value of type <b>ULONGLONG</b> to a value of type <b>LONG</b>.

## Syntax

````
NTSTATUS RtlULongLongToLong(
  _In_  ULONGLONG ullOperand,
  _Out_ LONG      *plResult
);
````

## Parameters

`ullOperand`

The value to be converted.

`plResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |