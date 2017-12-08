---
UID: NF.ntintsafe.RtlSSIZETSub
title: RtlSSIZETSub function
author: windows-driver-content
description: Subtracts one value of type SSIZE_T from another.
old-location: kernel\rtlssizetsub.htm
old-project: kernel
ms.assetid: 6EFDD7BF-B347-4E02-905E-01F0F155DB6F
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlSSIZETSub
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
req.alt-api: RtlSSIZETSub
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

# RtlSSIZETSub function



## -description
Subtracts one value of type <b>SSIZE_T</b> from another.


## -syntax

````
NTSTATUS RtlSSIZETSub(
  _In_  SSIZE_T Minuend,
  _In_  SSIZE_T Subtrahend,
  _Out_ SSIZE_T *pResult
);
````


## -parameters

### -param Minuend [in]

The value from which <i>Subtrahend</i> is subtracted.

### -param Subtrahend [in]

The value to subtract from <i>Minuend</i>.

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