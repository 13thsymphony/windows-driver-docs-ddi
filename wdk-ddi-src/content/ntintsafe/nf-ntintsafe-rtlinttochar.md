---
UID: NF.ntintsafe.RtlIntToChar
title: RtlIntToChar function
author: windows-driver-content
description: Converts a value of type INT to a value of type CHAR.
old-location: kernel\rtlinttochar.htm
old-project: kernel
ms.assetid: 407237E2-2CDB-40D5-867C-1EA8E1D80065
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlIntToChar
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
req.alt-api: RtlIntToChar
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

# RtlIntToChar function



## -description
Converts a value of type <b>INT</b> to a value of type <b>CHAR</b>.


## -syntax

````
NTSTATUS RtlIntToChar(
  _In_  INT  iOperand,
  _Out_ CHAR *pch
);
````


## -parameters

### -param iOperand [in]

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