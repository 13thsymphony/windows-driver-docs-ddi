---
UID: NF:ntintsafe.RtlShortToUShort
title: RtlShortToUShort function
author: windows-driver-content
description: Converts a value of type SHORT to a value of type USHORT.
old-location: kernel\rtlshorttoushort.htm
old-project: kernel
ms.assetid: 6FD7C994-822A-422C-82D8-768BA842B2B2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlShortToUShort, ntintsafe/RtlShortToUShort, kernel.rtlshorttoushort, RtlShortToUShort function [Kernel-Mode Driver Architecture]
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
-	RtlShortToUShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlShortToUShort function
Converts a value of type <b>SHORT</b> to a value of type <b>USHORT</b>.

## Syntax

````
NTSTATUS RtlShortToUShort(
  _In_  SHORT  sOperand,
  _Out_ USHORT *pusResult
);
````

## Parameters

`sOperand`

The value to be converted.

`pusResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlShortToUInt16
</li>
<li>RtlShortToWord
</li>
<li>RtlInt16ToUShort
</li>
<li>RtlInt16ToUInt16
</li>
<li>RtlInt16ToWord
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |