---
UID: NF:ntintsafe.RtlIntToUShort
title: RtlIntToUShort function
author: windows-driver-content
description: Converts a value of type INT to a value of type USHORT.
old-location: kernel\rtlinttoushort.htm
old-project: kernel
ms.assetid: 52571477-80F5-4848-8BCC-AFA70140FABE
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntintsafe/RtlIntToUShort, RtlIntToUShort function [Kernel-Mode Driver Architecture], kernel.rtlinttoushort, RtlIntToUShort
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
-	RtlIntToUShort
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlIntToUShort function
Converts a value of type <b>INT</b> to a value of type <b>USHORT</b>.

## Syntax

````
NTSTATUS RtlIntToUShort(
  _In_  INT    iOperand,
  _Out_ USHORT *pusResult
);
````

## Parameters

`iOperand`

The value to be converted.

`pusResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlIntToUInt16
</li>
<li>RtlIntToWord
</li>
<li>RtlInt32ToUShort
</li>
<li>RtlInt32ToUInt16
</li>
<li>RtlInt32ToWord
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |