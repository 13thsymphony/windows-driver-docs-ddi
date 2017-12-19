---
UID: NF.ntintsafe.RtlLongToInt
title: RtlLongToInt function
author: windows-driver-content
description: Converts a value of type LONG to a value of type INT.
old-location: kernel\rtllongtoint.htm
old-project: kernel
ms.assetid: 9C35B77E-FFEC-42A0-9D2C-9E52E210C941
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlLongToInt
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
req.alt-api: RtlLongToInt
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

# RtlLongToInt function



## -description
Converts a value of type <b>LONG</b> to a value of type <b>INT</b>.



## -syntax

````
NTSTATUS RtlLongToInt(
  _In_  LONG lOperand,
  _Out_ INT  *piResult
);
````


## -parameters

### -param lOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

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