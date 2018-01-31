---
UID : NF:ntintsafe.RtlIntToShort
title : RtlIntToShort function
author : windows-driver-content
description : Converts a value of type INT to a value of type SHORT.
old-location : kernel\rtlinttoshort.htm
old-project : kernel
ms.assetid : E8E05F9B-2F83-4537-979E-024E8412D733
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ntintsafe/RtlIntToShort, kernel.rtlinttoshort, RtlIntToShort, RtlIntToShort function [Kernel-Mode Driver Architecture]
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


# RtlIntToShort function
Converts a value of type <b>INT</b> to a value of type <b>SHORT</b>.

## Syntax

````
NTSTATUS RtlIntToShort(
  _In_  INT   iOperand,
  _Out_ SHORT *psResult
);
````

## Parameters

`iOperand`

The value to be converted.

`psResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlIntToInt16
</li>
<li>RtlInt32ToShort
</li>
<li>RtlInt32ToInt16
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