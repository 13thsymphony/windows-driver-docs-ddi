---
UID : NF:ntintsafe.RtlIntPtrToULongLong
title : RtlIntPtrToULongLong function
author : windows-driver-content
description : Converts a value of type INT_PTR to a value of type ULONGLONG.
old-location : kernel\rtlintptrtoulonglong.htm
old-project : kernel
ms.assetid : FF5D7B10-86AE-4C01-AFA9-C0C94E566428
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlIntPtrToULongLong
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
req.alt-api : RtlIntPtrToULongLong
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


# RtlIntPtrToULongLong function
Converts a value of type <b>INT_PTR</b> to a value of type <b>ULONGLONG</b>.

## Syntax

````
NTSTATUS RtlIntPtrToULongLong(
  _In_  INT_PTR   iOperand,
  _Out_ ULONGLONG *pullResult
);
````

## Parameters

`iOperand`

The value to be converted.

`pullResult`

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