---
UID: NF:ntintsafe.RtlULongPtrToLongLong
title: RtlULongPtrToLongLong function
author: windows-driver-content
description: Converts a value of type ULONG_PTR to a value of type LONGLONG.
old-location: kernel\rtlulongptrtolonglong.htm
old-project: kernel
ms.assetid: 55DB2888-8427-4714-A72C-1F0C2804C3EA
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlULongPtrToLongLong
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
req.alt-api: RtlULongPtrToLongLong
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
req.typenames: PUBLIC_OBJECT_TYPE_INFORMATION, *PPUBLIC_OBJECT_TYPE_INFORMATION
---

# RtlULongPtrToLongLong function



## -description
Converts a value of type <b>ULONG_PTR</b> to a value of type <b>LONGLONG</b>.



## -syntax

````
NTSTATUS RtlULongPtrToLongLong(
  _In_  ULONG_PTR ulOperand,
  _Out_ LONGLONG  *pllResult
);
````


## -parameters

### -param ulOperand [in]

The value to be converted.


### -param pllResult [out]

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