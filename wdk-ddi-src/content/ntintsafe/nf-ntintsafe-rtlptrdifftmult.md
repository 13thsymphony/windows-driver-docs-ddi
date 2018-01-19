---
UID : NF:ntintsafe.RtlPtrdiffTMult
title : RtlPtrdiffTMult function
author : windows-driver-content
description : Multiplies one value of type PTRDIFF_T by another.
old-location : kernel\rtlptrdifftmult.htm
old-project : kernel
ms.assetid : 71F6D886-D32E-4C90-B5BA-A4A1BBCD0B8F
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlPtrdiffTMult
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
req.alt-api : RtlPtrdiffTMult
req.alt-loc : Ntintsafe.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlPtrdiffTMult function
Multiplies one value of type <b>PTRDIFF_T</b> by another.

## Syntax

````
NTSTATUS RtlPtrdiffTMult(
  _In_  PTRDIFF_T Multiplicand,
  _In_  PTRDIFF_T Multiplier,
  _Out_ PTRDIFF_T *pResult
);
````

## Parameters

`Multiplicand`

The value to be multiplied by <i>Multiplier</i>.

`Multiplier`

The value by which to multiply <i>Multiplicand</i>.

`pResult`

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.</p>

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