---
UID : NF:ntintsafe.RtlIntToUInt
title : RtlIntToUInt function
author : windows-driver-content
description : Converts a value of type INT to a value of type UINT.
old-location : kernel\rtlinttouint.htm
old-project : kernel
ms.assetid : 9D2C7E0F-99E2-4B95-8CB6-9158DA1D906F
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlIntToUInt, kernel.rtlinttouint, RtlIntToUInt function [Kernel-Mode Driver Architecture], ntintsafe/RtlIntToUInt
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


# RtlIntToUInt function
Converts a value of type <b>INT</b> to a value of type <b>UINT</b>.

## Syntax

````
NTSTATUS RtlIntToUInt(
  _In_  INT  iOperand,
  _Out_ UINT *puResult
);
````

## Parameters

`iOperand`

The value to be converted.

`puResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlIntToUIntPtr
</li>
<li>RtlInt32ToUInt
</li>
<li>RtlInt32ToUInt32
</li>
<li>RtlIntToSizeT
</li>
<li>RtlInt32ToUIntPtr
</li>
<li>RtlInt32ToSizeT
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