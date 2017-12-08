---
UID: NF.ntintsafe.RtlLongLongToChar
title: RtlLongLongToChar function
author: windows-driver-content
description: Converts a value of type LONGLONG to a value of type CHAR.
old-location: kernel\rtllonglongtochar.htm
old-project: kernel
ms.assetid: E69889FC-11EF-4C49-A550-7C9C9FE1FDA7
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlLongLongToChar
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
req.alt-api: RtlLongLongToChar
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

# RtlLongLongToChar function



## -description
Converts a value of type <b>LONGLONG</b> to a value of type <b>CHAR</b>.


## -syntax

````
NTSTATUS RtlLongLongToChar(
  _In_  LONGLONG llOperand,
  _Out_ CHAR     *pch
);
````


## -parameters

### -param llOperand [in]

The value to be converted.

### -param pch [out]

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