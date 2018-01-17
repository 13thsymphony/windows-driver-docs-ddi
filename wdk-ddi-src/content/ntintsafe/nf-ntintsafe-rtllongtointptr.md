---
UID: NF:ntintsafe.RtlLongToIntPtr
title: RtlLongToIntPtr function
author: windows-driver-content
description: Converts a value of type LONG to a value of type INT_PTR.
old-location: kernel\rtllongtointptr.htm
old-project: kernel
ms.assetid: E583418C-7A23-4F88-A3D2-E2BA11578079
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlLongToIntPtr
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
req.alt-api: RtlLongToIntPtr
req.alt-loc: Ntintsafe.h
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
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlLongToIntPtr function



## -description
Converts a value of type <b>LONG</b> to a value of type <b>INT_PTR</b>.



## -syntax

````
NTSTATUS RtlLongToIntPtr(
  _In_  LONG    lOperand,
  _Out_ INT_PTR *piResult
);
````


## -parameters

### -param lOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:</p>