---
UID: NF.ntintsafe.RtlULongToUShort
title: RtlULongToUShort function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type USHORT.
old-location: kernel\rtlulongtoushort.htm
old-project: kernel
ms.assetid: 6D03736F-E972-4A76-935A-BB8682DC38B8
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: RtlULongToUShort
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
req.alt-api: RtlULongToUShort
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

# RtlULongToUShort function



## -description
Converts a value of type <b>ULONG</b> to a value of type <b>USHORT</b>.



## -syntax

````
NTSTATUS RtlULongToUShort(
  _In_  ULONG  ulOperand,
  _Out_ USHORT *pusResult
);
````


## -parameters

### -param ulOperand [in]

The value to be converted.


### -param pusResult [out]

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