---
UID : NF:ntintsafe.RtlLongLongToIntPtr
title : RtlLongLongToIntPtr function
author : windows-driver-content
description : Converts a value of type LONGLONG to a value of type INT_PTR.
old-location : kernel\rtllonglongtointptr.htm
old-project : kernel
ms.assetid : 7BFAB50B-7C0A-40D8-AB6D-ECBBDA0387AA
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlLongLongToIntPtr
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
req.alt-api : RtlLongLongToIntPtr
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


# RtlLongLongToIntPtr function
Converts a value of type <b>LONGLONG</b> to a value of type <b>INT_PTR</b>.

## Syntax

````
NTSTATUS RtlLongLongToIntPtr(
  _In_  LONGLONG llOperand,
  _Out_ INT_PTR  *piResult
);
````

## Parameters

`llOperand`

The value to be converted.

`piResult`

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