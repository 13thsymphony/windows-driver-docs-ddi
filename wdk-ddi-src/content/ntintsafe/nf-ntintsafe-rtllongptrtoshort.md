---
UID: NF.ntintsafe.RtlLongPtrToShort
title: RtlLongPtrToShort function
author: windows-driver-content
description: Converts a value of type LONG_PTR to a value of type SHORT.
old-location: kernel\rtllongptrtoshort.htm
old-project: kernel
ms.assetid: 934967A0-9CEF-4377-9505-EE4C4E9AF706
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: RtlLongPtrToShort
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
req.alt-api: RtlLongPtrToShort
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

# RtlLongPtrToShort function



## -description
Converts a value of type <b>LONG_PTR</b> to a value of type <b>SHORT</b>.



## -syntax

````
NTSTATUS RtlLongPtrToShort(
  _In_  LONG_PTR lOperand,
  _Out_ SHORT    *psResult
);
````


## -parameters

### -param lOperand [in]

The value to be converted.


### -param psResult [out]

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