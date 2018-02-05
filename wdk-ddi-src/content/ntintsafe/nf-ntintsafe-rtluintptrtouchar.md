---
UID : NF:ntintsafe.RtlUIntPtrToUChar
title : RtlUIntPtrToUChar function
author : windows-driver-content
description : Converts a value of type UINT_PTR to a value of type UCHAR.
old-location : kernel\rtluintptrtouchar.htm
old-project : kernel
ms.assetid : F5E4225F-4C66-44A8-9445-7D7DBAFA1DA4
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlUIntPtrToUChar function [Kernel-Mode Driver Architecture], ntintsafe/RtlUIntPtrToUChar, kernel.rtluintptrtouchar, RtlUIntPtrToUChar
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


# RtlUIntPtrToUChar function
Converts a value of type <b>UINT_PTR</b> to a value of type <b>UCHAR</b>.

## Syntax

````
NTSTATUS RtlUIntPtrToUChar(
  _In_  UINT_PTR uOperand,
  _Out_ UCHAR    *pch
);
````

## Parameters

`uOperand`

The value to be converted.

`pch`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlSizeTToUChar
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |