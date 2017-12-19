---
UID: NF.ntintsafe.RtlUIntSub
title: RtlUIntSub function
author: windows-driver-content
description: Subtracts one value of type UINT from another.
old-location: kernel\rtluintsub.htm
old-project: kernel
ms.assetid: 0886578A-C1CF-4A48-86A3-407A0C16ADEC
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlUIntSub
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
req.alt-api: RtlUIntSub
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

# RtlUIntSub function



## -description
Subtracts one value of type <b>UINT</b> from another.



## -syntax

````
NTSTATUS RtlUIntSub(
  _In_  UINT uMinuend,
  _In_  UINT uSubtrahend,
  _Out_ UINT *puResult
);
````


## -parameters

### -param uMinuend [in]

The value from which <i>u8Subtrahend</i> is subtracted.


### -param uSubtrahend [in]

The value to subtract from <i>u8Minuend</i>.


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