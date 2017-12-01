---
UID: NF.ntintsafe.RtlUInt8ToInt8
title: RtlUInt8ToInt8
author: windows-driver-content
description: Converts a value of type UINT8 to a value of type INT8.
old-location: kernel\rtluint8toint8.htm
old-project: kernel
ms.assetid: 92666A78-DC2C-4B0B-B5D3-E724F342D151
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlUInt8ToInt8
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
req.alt-api: RtlUInt8ToInt8
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

# RtlUInt8ToInt8 function



## -description
<p>Converts a value of type <b>UINT8</b> to a value of type <b>INT8</b>.</p>


## -syntax

````
NTSTATUS RtlUInt8ToInt8(
  _In_  UINT8 u8Operand,
  _Out_ INT8  *pi8Result
);
````


## -parameters
<dl>

### -param <i>u8Operand</i> [in]

<dd>
<p>The value to be converted.</p>
</dd>

### -param <i>pi8Result</i> [out]

<dd>
<p>A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>
</dd>
</dl>

## -remarks
<p>This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.</p>

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