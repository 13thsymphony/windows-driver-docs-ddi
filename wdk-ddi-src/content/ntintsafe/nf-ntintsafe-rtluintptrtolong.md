---
UID: NF:ntintsafe.RtlUIntPtrToLong
title: RtlUIntPtrToLong function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type LONG.
old-location: kernel\rtluintptrtolong.htm
old-project: kernel
ms.assetid: 03138EBA-F041-47E4-B379-25A96B04E491
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlUIntPtrToLong, ntintsafe/RtlUIntPtrToLong, RtlUIntPtrToLong function [Kernel-Mode Driver Architecture], kernel.rtluintptrtolong
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
-	RtlUIntPtrToLong
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlUIntPtrToLong function
Converts a value of type <b>UINT_PTR</b> to a value of type <b>LONG</b>.

## Syntax

````
NTSTATUS RtlUIntPtrToLong(
  _In_  UINT_PTR UOperand,
  _Out_ LONG     *plResult
);
````

## Parameters

`uOperand`

TBD

`plResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlSizeTToLong
</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |
| **Library** | NtosKrnl.exe |