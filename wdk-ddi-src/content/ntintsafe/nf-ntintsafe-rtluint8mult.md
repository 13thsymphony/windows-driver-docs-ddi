---
UID: NF:ntintsafe.RtlUInt8Mult
title: RtlUInt8Mult function
author: windows-driver-content
description: Multiplies one value of type UINT8 by another.
old-location: kernel\rtluint8mult.htm
old-project: kernel
ms.assetid: 3F9E47F5-1DE3-4949-BE92-8C8F571BFD3D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUInt8Mult
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
req.alt-api: RtlUInt8Mult
req.alt-loc: ntintsafe.h
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

# RtlUInt8Mult function



## -description
Multiplies one value of type <b>UINT8</b> by another.



## -syntax

````
NTSTATUS RtlUInt8Mult(
  _In_  UINT8 u8Multiplicand,
  _In_  UINT8 u8Multiplier,
  _Out_ UINT8 *pu8Result
);
````


## -parameters

### -param u8Multiplicand [in]

The value to be multiplied by <i>u8Multiplier</i>.


### -param u8Multiplier [in]

The value by which to multiply <i>u8Multiplicand</i>.


### -param pu8Result [out]

A pointer to the result. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.


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