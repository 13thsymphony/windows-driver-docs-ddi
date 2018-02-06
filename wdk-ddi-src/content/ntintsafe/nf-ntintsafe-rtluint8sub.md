---
UID: NF:ntintsafe.RtlUInt8Sub
title: RtlUInt8Sub function
author: windows-driver-content
description: The RtlUInt8Sub routine subtracts one value of type UINT8 from another.
old-location: kernel\rtluint8sub.htm
old-project: kernel
ms.assetid: D8BD24AA-64CF-42CB-8AD2-2B6C77D4B195
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUInt8Sub, ntintsafe/RtlUInt8Sub, RtlUInt8Sub function [Kernel-Mode Driver Architecture], kernel.rtluint8sub
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
-	RtlUInt8Sub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUInt8Sub function
The <b>RtlUInt8Sub</b> routine subtracts one value of type <b>UINT8</b> from another.

## Syntax

````
NTSTATUS RtlUInt8Sub(
  _In_  UINT8 u8Minuend,
  _In_  UINT8 u8Subtrahend,
  _Out_ UINT8 *pu8Result
);
````

## Parameters

`u8Minuend`

The value from which <i>u8Subtrahend</i> is subtracted.

`u8Subtrahend`

The value to subtract from <i>u8Minuend</i>.

`pu8Result`

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

<b>RtlUInt8Sub</b> returns STATUS_SUCCESS if the routine is successful. Possible error return values include the following status code.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
An arithmetic overflow occurred.

</td>
</tr>
</table>

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |