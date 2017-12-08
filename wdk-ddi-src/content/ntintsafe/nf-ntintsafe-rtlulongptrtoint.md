---
UID: NF.ntintsafe.RtlULongPtrToInt
title: RtlULongPtrToInt function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type INT.
old-location: kernel\rtlulongptrtoint.htm
old-project: kernel
ms.assetid: 722A6A13-CAF0-46F3-936A-6E09480D4AC3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlULongPtrToInt
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
req.alt-api: RtlULongPtrToInt
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

# RtlULongPtrToInt function



## -description
Converts a value of type <b>ULONG_PTR</b> to a value of type <b>INT</b>.


## -syntax

````
NTSTATUS RtlULongPtrToInt(
  _In_  ULONG_PTR ulOperand,
  _Out_ INT       *piResult
);
````


## -parameters

### -param ulOperand [in]

The value to be converted.

### -param piResult [out]

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