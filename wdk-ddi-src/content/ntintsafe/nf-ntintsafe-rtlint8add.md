---
UID: NF:ntintsafe.RtlInt8Add
title: RtlInt8Add function
author: windows-driver-content
description: Adds two values of type INT8.
old-location: kernel\rtlint8add.htm
old-project: kernel
ms.assetid: E97C3EA9-2244-458E-BE5E-6312023118A3
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlInt8Add
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
req.alt-api: RtlInt8Add
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

# RtlInt8Add function



## -description
Adds two values of type <b>INT8</b>.



## -syntax

````
NTSTATUS RtlInt8Add(
  _In_  INT8 i8Augend,
  _In_  INT8 i8Addend,
  _Out_ INT8 *pi8Result
);
````


## -parameters

### -param i8Augend [in]

The first value in the equation.


### -param i8Addend [in]

The value to add to <i>i8Augend</i>.


### -param pi8Result [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


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