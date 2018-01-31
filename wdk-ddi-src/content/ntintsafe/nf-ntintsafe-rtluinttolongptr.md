---
UID : NF:ntintsafe.RtlUIntToLongPtr
title : RtlUIntToLongPtr function
author : windows-driver-content
description : Converts a value of type UINT to a value of type LONG_PTR.
old-location : kernel\rtluinttolongptr.htm
old-project : kernel
ms.assetid : B5EA3406-928E-436C-87F9-1C301CB7F592
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ntintsafe/RtlUIntToLongPtr, RtlUIntToLongPtr, RtlUIntToLongPtr function [Kernel-Mode Driver Architecture], kernel.rtluinttolongptr
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


# RtlUIntToLongPtr function
Converts a value of type <b>UINT</b> to a value of type <b>LONG_PTR</b>.

## Syntax

````
NTSTATUS RtlUIntToLongPtr(
  _In_  UINT     uOperand,
  _Out_ LONG_PTR *plResult
);
````

## Parameters

`uOperand`

The value to be converted.

`plResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>RtlUIntToSSIZET
</li>
<li>RtlUInt32ToLongPtr
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