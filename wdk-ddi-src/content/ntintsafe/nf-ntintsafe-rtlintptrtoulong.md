---
UID : NF:ntintsafe.RtlIntPtrToULong
title : RtlIntPtrToULong function
author : windows-driver-content
description : Converts a value of type INT_PTR to a value of type ULONG.
old-location : kernel\rtlintptrtoulong.htm
old-project : kernel
ms.assetid : 755F23FE-12F8-4A14-B2E2-746774B86342
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlIntPtrToULong function [Kernel-Mode Driver Architecture], ntintsafe/RtlIntPtrToULong, kernel.rtlintptrtoulong, RtlIntPtrToULong
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


# RtlIntPtrToULong function
Converts a value of type <b>INT_PTR</b> to a value of type <b>ULONG</b>.

## Syntax

````
NTSTATUS RtlIntPtrToULong(
  _In_  INT_PTR iOperand,
  _Out_ ULONG   *pulResult
);
````

## Parameters

`iOperand`

The value to be converted.

`pulResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlIntPtrToDWord
</li>
<li>RtlPtrdiffTToULong
</li>
<li>RtlPtrdiffTToDWord
</li>
</ul>

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