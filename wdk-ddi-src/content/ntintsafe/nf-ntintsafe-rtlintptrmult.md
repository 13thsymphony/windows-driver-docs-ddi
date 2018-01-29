---
UID : NF:ntintsafe.RtlIntPtrMult
title : RtlIntPtrMult function
author : windows-driver-content
description : Multiplies one value of type INT_PTR by another.
old-location : kernel\rtlintptrmult.htm
old-project : kernel
ms.assetid : F40C5DBB-8E52-471E-B010-A5EDFACDF773
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlIntPtrMult function [Kernel-Mode Driver Architecture], ntintsafe/RtlIntPtrMult, RtlIntPtrMult, kernel.rtlintptrmult
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


# RtlIntPtrMult function
Multiplies one value of type <b>INT_PTR</b> by another.

## Syntax

````
NTSTATUS RtlIntPtrMult(
  _In_  INT_PTR iMultiplicand,
  _In_  INT_PTR iMultiplier,
  _Out_ INT_PTR *piResult
);
````

## Parameters

`iMultiplicand`

The value to be multiplied by <i>iMultiplier</i>.

`iMultiplier`

The value by which to multiply <i>iMultiplicand</i>.

`piResult`

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

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