---
UID: NF.ntintsafe.RtlPtrdiffTSub
title: RtlPtrdiffTSub function
author: windows-driver-content
description: Subtracts one value of type PTRDIFF_T from another.
old-location: kernel\rtlptrdifftsub.htm
old-project: kernel
ms.assetid: C87E3BD5-8CA7-443E-8CC3-F863CD4F321A
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlPtrdiffTSub
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
req.alt-api: RtlPtrdiffTSub
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

# RtlPtrdiffTSub function



## -description
Subtracts one value of type <b>PTRDIFF_T</b> from another.



## -syntax

````
NTSTATUS RtlPtrdiffTSub(
  _In_  PTRDIFF_T Minuend,
  _In_  PTRDIFF_T Subtrahend,
  _Out_ PTRDIFF_T *pResult
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