---
UID: NF:ntintsafe.RtlUIntPtrAdd
title: RtlUIntPtrAdd function
author: windows-driver-content
description: Adds two values of type UINT_PTR.
old-location: kernel\rtluintptradd.htm
old-project: kernel
ms.assetid: 9106CE96-A26F-4358-9668-2C0E331BB793
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntintsafe/RtlUIntPtrAdd, RtlUIntPtrAdd, kernel.rtluintptradd, RtlUIntPtrAdd function [Kernel-Mode Driver Architecture]
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
-	RtlUIntPtrAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntPtrAdd function
Adds two values of type <b>UINT_PTR</b>.

## Syntax

````
NTSTATUS RtlUIntPtrAdd(
  _In_  UINT_PTR uAugend,
  _In_  UINT_PTR uAddend,
  _Out_ UINT_PTR *puResult
);
````

## Parameters

`uAugend`

The first value in the equation.

`uAddend`

The value to add to <i>uAugend</i>.

`puResult`

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlDWordAdd
</li>
<li>RtlUIntPtrAdd
</li>
<li>RtlULongPtrAdd
</li>
<li>RtlDWordPtrAdd
</li>
<li>RtlSIZETAdd
</li>
<li>RtlDWordLongAdd
</li>
<li>RtlULong64Add
</li>
<li>RtlDWord64Add
</li>
<li>RtlUInt64Add
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |