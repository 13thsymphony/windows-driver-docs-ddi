---
UID: NF:ntintsafe.RtlIntPtrToInt8
title: RtlIntPtrToInt8 function
author: windows-driver-content
description: Converts a value of type INT_PTR to a value of type INT8.
old-location: kernel\rtlintptrtoint8.htm
old-project: kernel
ms.assetid: 3AF29469-C376-4EF7-B8A0-88ADCA8FEE4F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlIntPtrToInt8
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
req.alt-api: RtlIntPtrToInt8
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

# RtlIntPtrToInt8 function



## -description
Converts a value of type <b>INT_PTR</b> to a value of type <b>INT8</b>.



## -syntax

````
NTSTATUS RtlIntPtrToInt8(
  _In_  INT_PTR iOperand,
  _Out_ INT8    *pi8Result
);
````


## -parameters

### -param iOperand [in]

The value to be converted.


### -param pi8Result [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntintsafe.h</dt>
</dl>
</td>
</tr>
</table>