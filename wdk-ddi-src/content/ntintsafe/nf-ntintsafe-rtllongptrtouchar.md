---
UID : NF:ntintsafe.RtlLongPtrToUChar
title : RtlLongPtrToUChar function
author : windows-driver-content
description : Converts a value of type LONG_PTR to a value of type UCHAR.
old-location : kernel\rtllongptrtouchar.htm
old-project : kernel
ms.assetid : 86E72C5E-9DB1-4EDD-A6B0-272D4622A500
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlLongPtrToUChar
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
req.alt-api : RtlLongPtrToUChar
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


# RtlLongPtrToUChar function
Converts a value of type <b>LONG_PTR</b> to a value of type <b>UCHAR</b>.

## Syntax

````
NTSTATUS RtlLongPtrToUChar(
  _In_  LONG_PTR lOperand,
  _Out_ UCHAR    *pch
);
````

## Parameters

`lOperand`

The value to be converted.

`pch`

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