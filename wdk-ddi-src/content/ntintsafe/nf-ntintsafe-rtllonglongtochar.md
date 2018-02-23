---
UID: NF:ntintsafe.RtlLongLongToChar
title: RtlLongLongToChar function
author: windows-driver-content
description: Converts a value of type LONGLONG to a value of type CHAR.
old-location: kernel\rtllonglongtochar.htm
old-project: kernel
ms.assetid: E69889FC-11EF-4C49-A550-7C9C9FE1FDA7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.rtllonglongtochar, RtlLongLongToChar, ntintsafe/RtlLongLongToChar, RtlLongLongToChar function [Kernel-Mode Driver Architecture]
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
-	RtlLongLongToChar
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlLongLongToChar function
Converts a value of type <b>LONGLONG</b> to a value of type <b>CHAR</b>.

## Syntax

````
NTSTATUS RtlLongLongToChar(
  _In_  LONGLONG llOperand,
  _Out_ CHAR     *pch
);
````

## Parameters

`llOperand`

The value to be converted.

`pch`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlLong64ToChar
</li>
<li>RtlInt64ToChar
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |