---
UID: NF.ntintsafe.RtlDWordPtrAdd
title: RtlDWordPtrAdd function
author: windows-driver-content
description: Adds two values of type DWORD_PTR.
old-location: kernel\rtldwordptradd.htm
old-project: kernel
ms.assetid: 8364FC5F-1FF4-415F-B83C-4A866C860522
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: RtlDWordPtrAdd
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
req.alt-api: RtlDWordPtrAdd
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

# RtlDWordPtrAdd function



## -description
Adds two values of type <b>DWORD_PTR</b>.



## -syntax

````
NTSTATUS RtlDWordPtrAdd(
  _In_  DWORD_PTR dwAugend,
  _In_  DWORD_PTR dwAddend,
  _Out_ DWORD_PTR *pdwResult
);
````


## -parameters

### -param dwAugend [in]

The first value in the equation.


### -param dwAddend [in]

The value to add to <i>dwAugend</i>.


### -param pdwResult [out]

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