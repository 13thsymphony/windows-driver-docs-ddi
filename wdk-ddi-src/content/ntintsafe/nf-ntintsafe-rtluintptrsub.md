---
UID: NF:ntintsafe.RtlUIntPtrSub
title: RtlUIntPtrSub function
author: windows-driver-content
description: Subtracts one value of type UINT_PTR from another.
old-location: kernel\rtluintptrsub.htm
old-project: kernel
ms.assetid: D0E23A94-515B-4225-A8AC-390CDD3BEA60
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntintsafe/RtlUIntPtrSub, kernel.rtluintptrsub, RtlUIntPtrSub function [Kernel-Mode Driver Architecture], RtlUIntPtrSub
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
-	RtlUIntPtrSub
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntPtrSub function
Subtracts one value of type <b>UINT_PTR</b> from another.

## Syntax

````
NTSTATUS RtlUIntPtrSub(
  _In_  UINT_PTR uMinuend,
  _In_  UINT_PTR uSubtrahend,
  _Out_ UINT_PTR *puResult
);
````

## Parameters

`uMinuend`

The value from which <i>uSubtrahend</i> is subtracted.

`uSubtrahend`

The value to subtract from <i>uMinuend</i>.

`puResult`

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlUIntPtrSub
</li>
<li>RtlULongPtrSub
</li>
<li>RtlDWordPtrSub
</li>
<li>RtlSIZETSub
</li>
<li>RtlDWordLongSub
</li>
<li>RtlULong64Sub
</li>
<li>RtlDWord64Sub
</li>
<li>RtlUInt64Sub
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |