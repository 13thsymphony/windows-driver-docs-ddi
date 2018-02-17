---
UID: NF:ntintsafe.RtlULongLongToInt
title: RtlULongLongToInt function
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type INT.
old-location: kernel\rtlulonglongtoint.htm
old-project: kernel
ms.assetid: C52CB40D-0B3D-4ED9-99FD-464D23481AD3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongLongToInt, ntintsafe/RtlULongLongToInt, RtlULongLongToInt function [Kernel-Mode Driver Architecture], kernel.rtlulonglongtoint
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
-	RtlULongLongToInt
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongLongToInt function
Converts a value of type <b>ULONGLONG</b> to a value of type <b>INT</b>.

## Syntax

````
NTSTATUS RtlULongLongToInt(
  _In_  ULONGLONG ullOperand,
  _Out_ INT       *piResult
);
````

## Parameters

`ullOperand`

The value to be converted.

`piResult`

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