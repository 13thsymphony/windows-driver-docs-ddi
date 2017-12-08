---
UID: NF.ntintsafe.RtlULongPtrToUChar
title: RtlULongPtrToUChar function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type UCHAR.
old-location: kernel\rtlulongptrtouchar.htm
old-project: kernel
ms.assetid: 074159BD-EF74-45F9-B7A5-47F9E01E32C6
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlULongPtrToUChar
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
req.alt-api: RtlULongPtrToUChar
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

# RtlULongPtrToUChar function



## -description
Converts a value of type <b>ULONG_PTR</b> to a value of type <b>UCHAR</b>.


## -syntax

````
NTSTATUS RtlULongPtrToUChar(
  _In_  ULONG_PTR ulOperand,
  _Out_ UCHAR     *pch
);
````


## -parameters

### -param ulOperand [in]

The value to be converted.

### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

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