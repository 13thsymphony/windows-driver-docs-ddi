---
UID: NF:ntintsafe.RtlLongLongAdd
title: RtlLongLongAdd function
author: windows-driver-content
description: Adds two values of type LONGLONG.
old-location: kernel\rtllonglongadd.htm
old-project: kernel
ms.assetid: 94FD1DD3-0799-4E90-A115-9EF065433B05
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlLongLongAdd
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
req.alt-api: RtlLongLongAdd
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

# RtlLongLongAdd function



## -description
Adds two values of type <b>LONGLONG</b>.



## -syntax

````
NTSTATUS RtlLongLongAdd(
  _In_  LONGLONG llAugend,
  _In_  LONGLONG llAddend,
  _Out_ LONGLONG *pllResult
);
````


## -parameters

### -param llAugend [in]

The first value in the equation.


### -param llAddend [in]

The value to add to <i>llAugend</i>.


### -param pllResult [out]

A pointer to the sum. If the operation results in a value that overflows or underflows the capacity of the type, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks
This is one of a set of inline functions designed to provide arithmetic operations and perform validity checks with minimal impact on performance.

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