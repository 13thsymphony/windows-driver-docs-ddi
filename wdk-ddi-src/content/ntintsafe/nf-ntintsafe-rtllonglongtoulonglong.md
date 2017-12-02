---
UID: NF.ntintsafe.RtlLongLongToULongLong
title: RtlLongLongToULongLong
author: windows-driver-content
description: Converts a value of type LONGLONG to a value of type LONGLONG.
old-location: kernel\rtllonglongtoulonglong.htm
old-project: kernel
ms.assetid: AE273E51-FEB5-4470-AB19-0F55A2F8EFFD
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlLongLongToULongLong
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
req.alt-api: RtlLongLongToULongLong
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

# RtlLongLongToULongLong function



## -description
<p>Converts a value of type <b>LONGLONG</b> to a value of type <b>LONGLONG</b>.</p>


## -syntax

````
NTSTATUS RtlLongLongToULongLong(
  _In_  LONGLONG llOperand,
  _Out_ LONGLONG *pullResult
);
````


## -parameters
<dl>

### -param llOperand [in]

<dd>
<p>The value to be converted.</p>
</dd>

### -param pullResult [out]

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