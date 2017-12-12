---
UID: NF.ntintsafe.RtlInt8ToUInt
title: RtlInt8ToUInt function
author: windows-driver-content
description: Converts a value of type INT8 to a value of type UINT.
old-location: kernel\rtlint8touint.htm
old-project: kernel
ms.assetid: 00C37CB5-4CBC-48C3-8D90-F01BF82E2EF6
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: RtlInt8ToUInt
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
req.alt-api: RtlInt8ToUInt
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

# RtlInt8ToUInt function



## -description
Converts a value of type <b>INT8</b> to a value of type <b>UINT</b>.



## -syntax

````
NTSTATUS RtlInt8ToUInt(
  _In_  INT8 i8Operand,
  _Out_ UINT *puResult
);
````


## -parameters

### -param i8Operand [in]

The value to be converted.


### -param puResult [out]

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