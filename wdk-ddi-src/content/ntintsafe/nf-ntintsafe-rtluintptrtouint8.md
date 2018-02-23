---
UID: NF:ntintsafe.RtlUIntPtrToUInt8
title: RtlUIntPtrToUInt8 function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type UINT8.
old-location: kernel\rtluintptrtouint8.htm
old-project: kernel
ms.assetid: D6705580-F3BB-44D0-8B6F-114F156FF915
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.rtluintptrtouint8, RtlUIntPtrToUInt8 function [Kernel-Mode Driver Architecture], ntintsafe/RtlUIntPtrToUInt8, RtlUIntPtrToUInt8
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
-	RtlUIntPtrToUInt8
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntPtrToUInt8 function
Converts a value of type <b>UINT_PTR</b> to a value of type <b>UINT8</b>.

## Syntax

````
NTSTATUS RtlUIntPtrToUInt8(
  _In_  UINT_PTR uOperand,
  _Out_ UINT8    *pu8Result
);
````

## Parameters

`uOperand`

The value to be converted.

`pu8Result`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlUIntPtrToByte
</li>
<li>RtlSizeTToUInt8
</li>
<li>RtlSizeTToByte
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |