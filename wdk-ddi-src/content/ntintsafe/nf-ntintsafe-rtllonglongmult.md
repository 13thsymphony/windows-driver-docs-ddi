---
UID: NF.ntintsafe.RtlLongLongMult
title: RtlLongLongMult function
author: windows-driver-content
description: Multiplies one value of type LONGLONG by another.
old-location: kernel\rtllonglongmult.htm
old-project: kernel
ms.assetid: E5FE5EDB-D11D-4EF7-9CEA-CF059398A063
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: RtlLongLongMult
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
req.alt-api: RtlLongLongMult
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

# RtlLongLongMult function



## -description
Multiplies one value of type <b>LONGLONG</b> by another.



## -syntax

````
NTSTATUS RtlLongLongMult(
  _In_  LONGLONG llMultiplicand,
  _In_  LONGLONG llMultiplier,
  _Out_ LONGLONG *pllResult
);
````


## -parameters

### -param llMultiplicand [in]

The value to be multiplied by <i>llMultiplier</i>.


### -param llMultiplier [in]

The value by which to multiply <i>llMultiplicand</i>.


### -param pllResult [out]

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