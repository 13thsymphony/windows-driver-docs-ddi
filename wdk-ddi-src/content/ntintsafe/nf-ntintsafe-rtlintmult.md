---
UID: NF.ntintsafe.RtlIntMult
title: RtlIntMult function
author: windows-driver-content
description: Multiplies one value of type INT by another.
old-location: kernel\rtlintmult.htm
old-project: kernel
ms.assetid: 5417D6B1-0523-4C01-9C07-571D096E10F3
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlIntMult
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
req.alt-api: RtlIntMult
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
---

# RtlIntMult function



## -description
Multiplies one value of type <b>INT</b> by another.



## -syntax

````
NTSTATUS RtlIntMult(
  _In_  INT iMultiplicand,
  _In_  INT iMultiplier,
  _Out_ INT *piResult
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