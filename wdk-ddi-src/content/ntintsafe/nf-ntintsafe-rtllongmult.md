---
UID: NF.ntintsafe.RtlLongMult
title: RtlLongMult function
author: windows-driver-content
description: Multiplies one value of type LONG by another.
old-location: kernel\rtllongmult.htm
old-project: kernel
ms.assetid: A95A88B6-066F-4489-B5C0-B012E831D7AD
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlLongMult
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
req.alt-api: RtlLongMult
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

# RtlLongMult function



## -description
Multiplies one value of type <b>LONG</b> by another.


## -syntax

````
NTSTATUS RtlLongMult(
  _In_  LONG lMultiplicand,
  _In_  LONG lMultiplier,
  _Out_ LONG *plResult
);
````


## -parameters

### -param lMultiplicand [in]

The value to be multiplied by <i>lMultiplier</i>.

### -param lMultiplier [in]

The value by which to multiply <i>lMultiplicand</i>.

### -param plResult [out]

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