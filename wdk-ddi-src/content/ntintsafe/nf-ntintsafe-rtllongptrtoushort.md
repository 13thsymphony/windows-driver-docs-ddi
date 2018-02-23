---
UID: NF:ntintsafe.RtlLongPtrToUShort
title: RtlLongPtrToUShort function
author: windows-driver-content
description: Converts a value of type LONG_PTR to a value of type USHORT.
old-location: kernel\rtllongptrtoushort.htm
old-project: kernel
ms.assetid: B003772E-9A9A-4EE0-BF8F-C956BCE7EDA5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlLongPtrToUShort, kernel.rtllongptrtoushort, RtlLongPtrToUShort function [Kernel-Mode Driver Architecture], ntintsafe/RtlLongPtrToUShort
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
-	RtlLongPtrToUShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlLongPtrToUShort function
Converts a value of type <b>LONG_PTR</b> to a value of type <b>USHORT</b>.

## Syntax

````
NTSTATUS RtlLongPtrToUShort(
  _In_  LONG_PTR lOperand,
  _Out_ USHORT   *pusResult
);
````

## Parameters

`lOperand`

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
RtlLongPtrToUInt16
</li>
<li>RtlLongPtrToWord
</li>
<li>RtlSSIZETToUShort
</li>
<li>RtlSSIZETToUInt16
</li>
<li>RtlSSIZETToWord
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |