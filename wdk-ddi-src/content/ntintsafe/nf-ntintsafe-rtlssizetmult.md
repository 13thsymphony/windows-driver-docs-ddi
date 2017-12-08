---
UID: NF.ntintsafe.RtlSSIZETMult
title: RtlSSIZETMult function
author: windows-driver-content
description: Multiplies one value of type SSIZE_T by another.
old-location: kernel\rtlssizetmult.htm
old-project: kernel
ms.assetid: 43FFE47F-C8A3-49B4-B61A-3EAF3841037D
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlSSIZETMult
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
req.alt-api: RtlSSIZETMult
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

# RtlSSIZETMult function



## -description
Multiplies one value of type <b>SSIZE_T</b> by another.


## -syntax

````
NTSTATUS RtlSSIZETMult(
  _In_  SSIZE_T Multiplicand,
  _In_  SSIZE_T Multiplier,
  _Out_ SSIZE_T *pResult
);
````


## -parameters

### -param Multiplicand [in]

The value to be multiplied by <i>Multiplier</i>.

### -param Multiplier [in]

The value by which to multiply <i>Multiplicand</i>.

### -param pResult [out]

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