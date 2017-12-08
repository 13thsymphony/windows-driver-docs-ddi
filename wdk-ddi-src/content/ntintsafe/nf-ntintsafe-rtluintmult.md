---
UID: NF.ntintsafe.RtlUIntMult
title: RtlUIntMult function
author: windows-driver-content
description: Multiplies one value of type UINT by another.
old-location: kernel\rtluintmult.htm
old-project: kernel
ms.assetid: 9972BC53-3CFB-4649-9C54-B194039D804F
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlUIntMult
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
req.alt-api: RtlUIntMult
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

# RtlUIntMult function



## -description
Multiplies one value of type <b>UINT</b> by another.


## -syntax

````
NTSTATUS RtlUIntMult(
  _In_  UINT uMultiplicand,
  _In_  UINT uMultiplier,
  _Out_ UINT *puResult
);
````


## -parameters

### -param uMultiplicand [in]

The value to be multiplied by <i>uMultiplier</i>.

### -param uMultiplier [in]

The value by which to multiply <i>uMultiplicand</i>.

### -param puResult [out]

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