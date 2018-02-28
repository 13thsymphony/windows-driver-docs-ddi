---
UID: NF:ntintsafe.RtlUIntAdd
title: RtlUIntAdd function
author: windows-driver-content
description: Adds two values of type UINT.
old-location: kernel\rtluintadd.htm
old-project: kernel
ms.assetid: ABF392BD-7B05-417E-AFD8-4EE7E64F9FC2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlUIntAdd, RtlUIntAdd function [Kernel-Mode Driver Architecture], kernel.rtluintadd, ntintsafe/RtlUIntAdd
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntintsafe.h
api_name:
-	RtlUIntAdd
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntAdd function
Adds two values of type <b>UINT</b>.

## Syntax

````
NTSTATUS RtlUIntAdd(
  _In_  UINT uAugend,
  _In_  UINT uAddend,
  _Out_ UINT *puResult
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
<li>
RtlUInt32Add
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |