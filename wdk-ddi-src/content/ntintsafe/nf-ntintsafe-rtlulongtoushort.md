---
UID: NF:ntintsafe.RtlULongToUShort
title: RtlULongToUShort function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type USHORT.
old-location: kernel\rtlulongtoushort.htm
old-project: kernel
ms.assetid: 6D03736F-E972-4A76-935A-BB8682DC38B8
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlULongToUShort, RtlULongToUShort function [Kernel-Mode Driver Architecture], kernel.rtlulongtoushort, ntintsafe/RtlULongToUShort
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
-	RtlULongToUShort
product:
- Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlULongToUShort function
Converts a value of type <b>ULONG</b> to a value of type <b>USHORT</b>.

## Syntax

```
NTSTATUS RtlULongToUShort(
  ULONG  ulOperand,
  USHORT *pusResult
);
```

## Parameters

`ulOperand`

The value to be converted.

`pusResult`

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