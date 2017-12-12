---
UID: NF.ntintsafe.RtlLongPtrToChar
title: RtlLongPtrToChar function
author: windows-driver-content
description: Converts a value of type LONG_PTR to a value of type CHAR.
old-location: kernel\rtllongptrtochar.htm
old-project: kernel
ms.assetid: 9DB98A1F-F820-4182-A22D-1C759A0F8F72
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: RtlLongPtrToChar
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
req.alt-api: RtlLongPtrToChar
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

# RtlLongPtrToChar function



## -description
Converts a value of type <b>LONG_PTR</b> to a value of type <b>CHAR</b>.



## -syntax

````
NTSTATUS RtlLongPtrToChar(
  _In_  LONG_PTR lOperand,
  _Out_ CHAR     *pch
);
````


## -parameters

### -param lOperand [in]

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