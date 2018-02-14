---
UID: NF:ntintsafe.RtlUShortToChar
title: RtlUShortToChar function
author: windows-driver-content
description: Converts a value of type USHORT to a value of type CHAR.
old-location: kernel\rtlushorttochar.htm
old-project: kernel
ms.assetid: 13C5988F-1669-4B18-9423-74587276320F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUShortToChar, kernel.rtlushorttochar, RtlUShortToChar function [Kernel-Mode Driver Architecture], ntintsafe/RtlUShortToChar
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
-	RtlUShortToChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUShortToChar function
Converts a value of type <b>USHORT</b> to a value of type <b>CHAR</b>.

## Syntax

````
NTSTATUS RtlUShortToChar(
  _In_  USHORT usOperand,
  _Out_ CHAR   *pch
);
````

## Parameters

`usOperand`

The value to be converted.

`pch`

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