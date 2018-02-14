---
UID: NF:ntintsafe.RtlLongToULongLong
title: RtlLongToULongLong function
author: windows-driver-content
description: Converts a value of type LONG to a value of type ULONGLONG.
old-location: kernel\rtllongtoulonglong.htm
old-project: kernel
ms.assetid: 372B00C3-E5BD-4B2B-BB6B-F07878D661B4
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlLongToULongLong function [Kernel-Mode Driver Architecture], ntintsafe/RtlLongToULongLong, RtlLongToULongLong, kernel.rtllongtoulonglong
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
-	RtlLongToULongLong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlLongToULongLong function
Converts a value of type <b>LONG</b> to a value of type <b>ULONGLONG</b>.

## Syntax

````
NTSTATUS RtlLongToULongLong(
  _In_  LONG      lOperand,
  _Out_ ULONGLONG *pullResult
);
````

## Parameters

`lOperand`

The value to be converted.

`pullResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlLongToDWordLong
</li>
<li>RtlLongToULong64
</li>
<li>RtlLongToDWord64
</li>
<li>RtlLongToUInt64
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |