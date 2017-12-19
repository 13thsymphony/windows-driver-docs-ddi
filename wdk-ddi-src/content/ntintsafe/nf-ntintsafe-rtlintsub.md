---
UID: NF.ntintsafe.RtlIntSub
title: RtlIntSub function
author: windows-driver-content
description: Subtracts one value of type INT from another.
old-location: kernel\rtlintsub.htm
old-project: kernel
ms.assetid: 68BBD6B8-5C7C-4FE5-97F7-473A9510400F
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlIntSub
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
req.alt-api: RtlIntSub
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

# RtlIntSub function



## -description
Subtracts one value of type <b>INT</b> from another.



## -syntax

````
NTSTATUS RtlIntSub(
  _In_  INT iMinuend,
  _In_  INT iSubtrahend,
  _Out_ INT *pu8Result
);
````


## -parameters

### -param iMinuend [in]

The value from which <i>iSubtrahend</i> is subtracted.


### -param iSubtrahend [in]

The value to subtract from <i>iMinuend</i>.


### -param pu8Result [out]

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