---
UID: NF:ntintsafe.RtlUIntPtrToUInt8
title: RtlUIntPtrToUInt8 function
author: windows-driver-content
description: Converts a value of type UINT_PTR to a value of type UINT8.
old-location: kernel\rtluintptrtouint8.htm
old-project: kernel
ms.assetid: D6705580-F3BB-44D0-8B6F-114F156FF915
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUIntPtrToUInt8
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
req.alt-api: RtlUIntPtrToUInt8
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

# RtlUIntPtrToUInt8 function



## -description
Converts a value of type <b>UINT_PTR</b> to a value of type <b>UINT8</b>.



## -syntax

````
NTSTATUS RtlUIntPtrToUInt8(
  _In_  UINT_PTR uOperand,
  _Out_ UINT8    *pu8Result
);
````


## -parameters

### -param uOperand [in]

The value to be converted.


### -param pu8Result [out]

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