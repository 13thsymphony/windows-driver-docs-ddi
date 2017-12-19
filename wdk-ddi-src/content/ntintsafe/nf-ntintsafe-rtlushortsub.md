---
UID: NF.ntintsafe.RtlUShortSub
title: RtlUShortSub function
author: windows-driver-content
description: Subtracts one value of type USHORT from another.
old-location: kernel\rtlushortsub.htm
old-project: kernel
ms.assetid: 1C0392AE-F3BD-4F42-9094-87228B7C3E10
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: RtlUShortSub
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
req.alt-api: RtlUShortSub
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

# RtlUShortSub function



## -description
Subtracts one value of type <b>USHORT</b> from another.



## -syntax

````
NTSTATUS RtlUShortSub(
  _In_  USHORT usMinuend,
  _In_  USHORT usSubtrahend,
  _Out_ USHORT *pusResult
);
````


## -parameters

### -param usMinuend [in]

The value from which <i>usSubtrahend</i> is subtracted.


### -param usSubtrahend [in]

The value to subtract from <i>usMinuend</i>.


### -param pusResult [out]

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