---
UID : NF:ntintsafe.RtlUInt8ToChar
title : RtlUInt8ToChar function
author : windows-driver-content
description : Converts a value of type UINT8 to a value of type CHAR.
old-location : kernel\rtluint8tochar.htm
old-project : kernel
ms.assetid : 78EAB56F-8E6D-4048-83DC-1B9BC75E08B5
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlUInt8ToChar
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
req.alt-api : RtlUInt8ToChar
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


# RtlUInt8ToChar function
Converts a value of type <b>UINT8</b> to a value of type <b>CHAR</b>.

## Syntax

````
NTSTATUS RtlUInt8ToChar(
  _In_  UINT8 u8Operand,
  _Out_ CHAR  *pch
);
````

## Parameters

`u8Operand`

The value to be converted.

`pch`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.</p>

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