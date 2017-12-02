---
UID: NF.ntintsafe.RtlLongLongMult
title: RtlLongLongMult
author: windows-driver-content
description: Multiplies one value of type LONGLONG by another.
old-location: kernel\rtllonglongmult.htm
old-project: kernel
ms.assetid: E5FE5EDB-D11D-4EF7-9CEA-CF059398A063
ms.author: windowsdriverdev
ms.date: 11/28/2017
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
req.iface: 
---

# RtlLongLongMult function



## -description
<p>Multiplies one value of type <b>LONGLONG</b> by another.</p>


## -syntax

````
NTSTATUS RtlLongLongMult(
  _In_  LONGLONG llMultiplicand,
  _In_  LONGLONG llMultiplier,
  _Out_ LONGLONG *pllResult
);
````


## -parameters
<dl>

### -param llMultiplicand [in]

<dd>
<p>The value to be multiplied by <i>llMultiplier</i>.</p>
</dd>

### -param llMultiplier [in]

<dd>
<p>The value by which to multiply <i>llMultiplicand</i>.</p>
</dd>

### -param pllResult [out]

<dd>
<p>A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>
</dd>
</dl>

## -remarks
<p>This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.</p>

<p>This function uses the following alternate name:</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntintsafe.h</dt>
</dl>
</td>
</tr>
</table>