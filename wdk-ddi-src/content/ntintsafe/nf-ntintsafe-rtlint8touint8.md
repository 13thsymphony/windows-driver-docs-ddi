---
UID: NF.ntintsafe.RtlInt8ToUInt8
title: RtlInt8ToUInt8
author: windows-driver-content
description: Converts a value of type INT8 to a value of type UINT8.
old-location: kernel\rtlint8touint8.htm
old-project: kernel
ms.assetid: 884F36CD-8F2F-401C-A800-33735764B844
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: RtlInt8ToUInt8
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
req.alt-api: RtlInt8ToUInt8
req.alt-loc: ntintsafe.h
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

# RtlInt8ToUInt8 function



## -description
<p>Converts a value of type <b>INT8</b> to a value of type <b>UINT8</b>.</p>


## -syntax

````
NTSTATUS RtlInt8ToUInt8(
  _In_  INT8  i8Operand,
  _Out_ UINT8 *pu8Result
);
````


## -parameters
<dl>

### -param <i>i8Operand</i> [in]

<dd>
<p>The value to be converted.</p>
</dd>

### -param <i>pu8Result</i> [out]

<dd>
<p>A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>
</dd>
</dl>

## -remarks
<p>This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.</p>

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