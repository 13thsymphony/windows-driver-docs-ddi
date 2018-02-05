---
UID : NF:ntintsafe.RtlIntPtrToInt
title : RtlIntPtrToInt function
author : windows-driver-content
description : Converts a value of type INT_PTR to a value of type INT.
old-location : kernel\rtlintptrtoint.htm
old-project : kernel
ms.assetid : 96D932C6-B969-4C91-B4B1-6FEC7D4AD250
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ntintsafe/RtlIntPtrToInt, RtlIntPtrToInt, RtlIntPtrToInt function [Kernel-Mode Driver Architecture], kernel.rtlintptrtoint
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


# RtlIntPtrToInt function
Converts a value of type <b>INT_PTR</b> to a value of type <b>INT</b>.

## Syntax

````
NTSTATUS RtlIntPtrToInt(
  _In_  INT_PTR iOperand,
  _Out_ INT     *piResult
);
````

## Parameters

`iOperand`

The value to be converted.

`piResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlIntPtrToInt32
</li>
<li>RtlPtrdiffTToInt
</li>
<li>RtlPtrdiffTToInt32
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |