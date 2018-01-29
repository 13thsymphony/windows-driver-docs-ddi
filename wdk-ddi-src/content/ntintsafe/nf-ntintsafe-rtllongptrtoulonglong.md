---
UID : NF:ntintsafe.RtlLongPtrToULongLong
title : RtlLongPtrToULongLong function
author : windows-driver-content
description : Converts a value of type LONG_PTR to a value of type ULONGLONG.
old-location : kernel\rtllongptrtoulonglong.htm
old-project : kernel
ms.assetid : E0CAA44B-2432-4199-B2E6-8105FD7BA504
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ntintsafe/RtlLongPtrToULongLong, RtlLongPtrToULongLong function [Kernel-Mode Driver Architecture], kernel.rtllongptrtoulonglong, RtlLongPtrToULongLong
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


# RtlLongPtrToULongLong function
Converts a value of type <b>LONG_PTR</b> to a value of type <b>ULONGLONG</b>.

## Syntax

````
NTSTATUS RtlLongPtrToULongLong(
  _In_  LONG_PTR  lOperand,
  _Out_ ULONGLONG *pullResult
);
````

## Parameters

`lOperand`

The value to be converted.

`pullResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>
RtlLongPtrToDWordLong
</li>
<li>RtlLongPtrToULong64
</li>
<li>RtlLongPtrToDWord64
</li>
<li>RtlLongPtrToUInt64
</li>
<li>RtlSSIZETToULongLong
</li>
<li>RtlSSIZETToDWordLong
</li>
<li>RtlSSIZETToULong64
</li>
<li>RtlSSIZETToDWord64
</li>
<li>RtlSSIZETToUInt64
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