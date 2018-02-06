---
UID: NF:ntintsafe.RtlShortToULongPtr
title: RtlShortToULongPtr function
author: windows-driver-content
description: Converts a value of type SHORT to a value of type ULONG_PTR.
old-location: kernel\rtlshorttoulongptr.htm
old-project: kernel
ms.assetid: 0C279063-D5B1-4C82-8C0A-2B39E831BFB3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlshorttoulongptr, ntintsafe/RtlShortToULongPtr, RtlShortToULongPtr function [Kernel-Mode Driver Architecture], RtlShortToULongPtr
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
-	RtlShortToULongPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlShortToULongPtr function
Converts a value of type <b>SHORT</b> to a value of type <b>ULONG_PTR</b>.

## Syntax

````
NTSTATUS RtlShortToULongPtr(
  _In_  SHORT     sOperand,
  _Out_ ULONG_PTR *pulResult
);
````

## Parameters

`sOperand`

The value to be converted.

`pulResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:
<ul>
<li>
RtlLongLongToDWordPtr
</li>
<li>RtlLongLongToSIZET
</li>
<li>RtlLong64ToULongPtr
</li>
<li>RtlLong64ToDWordPtr
</li>
<li>RtlLong64ToSIZET
</li>
<li>RtlInt64ToULongPtr
</li>
<li>RtlInt64ToDWordPtr
</li>
<li>RtlInt64ToSIZET
</li>
<li>RtlShortToSIZET
</li>
<li>RtlInt16ToULongPtr
</li>
<li>RtlInt16ToDWordPtr
</li>
<li>RtlInt16ToSIZET
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |