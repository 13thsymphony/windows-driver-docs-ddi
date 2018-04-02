---
UID: NF:ntintsafe.RtlShortToDWordPtr
title: RtlShortToDWordPtr function
author: windows-driver-content
description: Converts a value of type SHORT to a value of type DWORD_PTR.
old-location: kernel\rtlshorttodwordptr.htm
old-project: kernel
ms.assetid: 0ABB3DBF-117D-491D-85A3-68E9280CFC6C
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlShortToDWordPtr, RtlShortToDWordPtr function [Kernel-Mode Driver Architecture], kernel.rtlshorttodwordptr, ntintsafe/RtlShortToDWordPtr
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntintsafe.h
api_name:
-	RtlShortToDWordPtr
product: Windows
targetos: Windows
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---


# RtlShortToDWordPtr function
Converts a value of type <b>SHORT</b> to a value of type <b>DWORD_PTR</b>.

## Syntax

```
NTSTATUS RtlShortToDWordPtr(
  SHORT     sOperand,
  DWORD_PTR *pdwResult
);
```

## Parameters

`sOperand`

The value to be converted.

`pdwResult`

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## Return Value

None

## Remarks

This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li></li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntintsafe.h |