---
UID : NF:ntintsafe.RtlLongLongAdd
title : RtlLongLongAdd function
author : windows-driver-content
description : Adds two values of type LONGLONG.
old-location : kernel\rtllonglongadd.htm
old-project : kernel
ms.assetid : 94FD1DD3-0799-4E90-A115-9EF065433B05
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlLongLongAdd function [Kernel-Mode Driver Architecture], RtlLongLongAdd, kernel.rtllonglongadd, ntintsafe/RtlLongLongAdd
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntintsafe.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlLongLongAdd function
Adds two values of type <b>LONGLONG</b>.

## Syntax

````
NTSTATUS RtlLongLongAdd(
  _In_  LONGLONG llAugend,
  _In_  LONGLONG llAddend,
  _Out_ LONGLONG *pllResult
);
````

## Parameters

`llAugend`

The first value in the equation.

`llAddend`

The value to add to <i>llAugend</i>.

`pllResult`

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlIntPtrAdd
</li>
<li>RtlLongPtrAdd
</li>
<li>RtlLong64Add
</li>
<li>RtlInt64Add
</li>
<li>RtlPtrdiffTAdd
</li>
<li>RtlSSIZETAdd
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntintsafe.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |