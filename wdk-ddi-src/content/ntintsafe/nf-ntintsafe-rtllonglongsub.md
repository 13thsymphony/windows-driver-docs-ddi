---
UID: NF:ntintsafe.RtlLongLongSub
title: RtlLongLongSub function
author: windows-driver-content
description: Subtracts one value of type LONGLONG from another.
old-location: kernel\rtllonglongsub.htm
old-project: kernel
ms.assetid: A0D35ECE-5B7F-4F60-9178-75673C9A945F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntintsafe/RtlLongLongSub, RtlLongLongSub function [Kernel-Mode Driver Architecture], RtlLongLongSub, kernel.rtllonglongsub
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
-	RtlLongLongSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlLongLongSub function
Subtracts one value of type <b>LONGLONG</b> from another.

## Syntax

````
NTSTATUS RtlLongLongSub(
  _In_  LONGLONG llMinuend,
  _In_  LONGLONG llSubtrahend,
  _Out_ LONGLONG *pllResult
);
````

## Parameters

`llMinuend`

The value from which <i>llSubtrahend</i> is subtracted.

`llSubtrahend`

The value to subtract from <i>llMinuend</i>.

`pllResult`

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlIntPtrSub
</li>
<li>RtlLongPtrSub
</li>
<li>RtlLong64Sub
</li>
<li>RtlInt64Sub
</li>
<li>RtlPtrdiffTSub
</li>
<li>RtlSSIZETSub
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |