---
UID: NF:ntintsafe.RtlIntPtrToULongPtr
title: RtlIntPtrToULongPtr function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type ULONG_PTR.
old-location: kernel\rtlintptrtoulongptr.htm
old-project: kernel
ms.assetid: DE6CD62F-0792-490A-9DDD-A979CAC0565A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlIntPtrToULongPtr, ntintsafe/RtlIntPtrToULongPtr, kernel.rtlintptrtoulongptr, RtlIntPtrToULongPtr function [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntintsafe.h
apiname:
-	RtlIntPtrToULongPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlIntPtrToULongPtr function
Converts a value of type <b>INT_PTR</b> to a value of type <b>ULONG_PTR</b>.

## Syntax

````
NTSTATUS RtlIntPtrToULongPtr(
  _In_  INT_PTR   iOperand,
  _Out_ ULONG_PTR *pulResult
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
<li>RtlIntPtrToDWordPtr
</li>
<li>RtlIntPtrToSIZET
</li>
<li>RtlPtrdiffTToULongPtr
</li>
<li>RtlPtrdiffTToDWordPtr
</li>
<li>RtlPtrdiffTToSIZET
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |