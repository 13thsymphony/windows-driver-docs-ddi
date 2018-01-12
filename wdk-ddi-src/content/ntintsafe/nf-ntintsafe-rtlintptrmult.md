---
UID: NF:ntintsafe.RtlIntPtrMult
title: RtlIntPtrMult function
author: windows-driver-content
description: Multiplies one value of type INT_PTR by another.
old-location: kernel\rtlintptrmult.htm
old-project: kernel
ms.assetid: F40C5DBB-8E52-471E-B010-A5EDFACDF773
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlIntPtrMult
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
req.alt-api: RtlIntPtrMult
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

# RtlIntPtrMult function



## -description
Multiplies one value of type <b>INT_PTR</b> by another.



## -syntax

````
NTSTATUS RtlIntPtrMult(
  _In_  INT_PTR iMultiplicand,
  _In_  INT_PTR iMultiplier,
  _Out_ INT_PTR *piResult
);
````


## -parameters

### -param iMultiplicand [in]

The value to be multiplied by <i>iMultiplier</i>.


### -param iMultiplier [in]

The value by which to multiply <i>iMultiplicand</i>.


### -param piResult [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.


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