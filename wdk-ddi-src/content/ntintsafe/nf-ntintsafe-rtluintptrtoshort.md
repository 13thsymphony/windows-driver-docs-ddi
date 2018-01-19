---
UID : NF:ntintsafe.RtlUIntPtrToShort
title : RtlUIntPtrToShort function
author : windows-driver-content
description : Converts a value of type UINT_PTR to a value of type SHORT.
old-location : kernel\rtluintptrtoshort.htm
old-project : kernel
ms.assetid : F381965B-0482-4D1A-874D-A1308812DB24
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlUIntPtrToShort
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
req.alt-api : RtlUIntPtrToShort
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


# RtlUIntPtrToShort function
Converts a value of type <b>UINT_PTR</b> to a value of type <b>SHORT</b>.

## Syntax

````
NTSTATUS RtlUIntPtrToShort(
  _In_  UINT_PTR uOperand,
  _Out_ SHORT    *psResult
);
````

## Parameters

`uOperand`

The value to be converted.

`psResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:</p>

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