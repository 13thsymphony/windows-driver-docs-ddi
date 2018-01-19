---
UID : NF:ntintsafe.RtlULongPtrAdd
title : RtlULongPtrAdd function
author : windows-driver-content
description : Adds two values of type ULONG_PTR.
old-location : kernel\rtlulongptradd.htm
old-project : kernel
ms.assetid : 26A9A0B6-07A3-4D42-A5A1-C4CDD541A3FA
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlULongPtrAdd
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
req.alt-api : RtlULongPtrAdd
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


# RtlULongPtrAdd function
Adds two values of type <b>ULONG_PTR</b>.

## Syntax

````
NTSTATUS RtlULongPtrAdd(
  _In_  ULONG_PTR ulAugend,
  _In_  ULONG_PTR ulAddend,
  _Out_ ULONG_PTR *pulResult
);
````

## Parameters

`ulAugend`

The first value in the equation.

`ulAddend`

The value to add to <i>ulAugend</i>.

`pulResult`

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None


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