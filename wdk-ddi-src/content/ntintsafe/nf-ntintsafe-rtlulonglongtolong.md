---
UID: NF.ntintsafe.RtlULongLongToLong
title: RtlULongLongToLong
author: windows-driver-content
description: Converts a value of type ULONGLONG to a value of type LONG.
old-location: kernel\rtlulonglongtolong.htm
old-project: kernel
ms.assetid: DC1784C6-0775-46E9-A439-B522713C297C
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlULongLongToLong
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
req.alt-api: RtlULongLongToLong
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

# RtlULongLongToLong function



## -description
<p>Converts a value of type <b>ULONGLONG</b> to a value of type <b>LONG</b>.</p>


## -syntax

````
NTSTATUS RtlULongLongToLong(
  _In_  ULONGLONG ullOperand,
  _Out_ LONG      *plResult
);
````


## -parameters
<dl>

### -param <i>ullOperand</i> [in]

<dd>
<p>The value to be converted.</p>
</dd>

### -param <i>plResult</i> [out]

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