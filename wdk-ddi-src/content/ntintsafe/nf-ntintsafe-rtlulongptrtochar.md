---
UID : NF:ntintsafe.RtlULongPtrToChar
title : RtlULongPtrToChar function
author : windows-driver-content
description : Converts a value of type ULONG_PTR to a value of type CHAR.
old-location : kernel\rtlulongptrtochar.htm
old-project : kernel
ms.assetid : DB015FC3-D263-4EA6-AAE1-E4ECA3ECF4F9
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.rtlulongptrtochar, RtlULongPtrToChar function [Kernel-Mode Driver Architecture], ntintsafe/RtlULongPtrToChar, RtlULongPtrToChar
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


# RtlULongPtrToChar function
Converts a value of type <b>ULONG_PTR</b> to a value of type <b>CHAR</b>.

## Syntax

````
NTSTATUS RtlULongPtrToChar(
  _In_  ULONG_PTR ulOperand,
  _Out_ CHAR      *pch
);
````

## Parameters

`ulOperand`

The value to be converted.

`pch`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

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