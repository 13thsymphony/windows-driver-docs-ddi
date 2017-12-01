---
UID: NF.ntintsafe.RtlLongPtrToUInt8
title: RtlLongPtrToUInt8
author: windows-driver-content
description: Converts a value of type LONG_PTR to a value of type UINT8.
old-location: kernel\rtllongptrtouint8.htm
old-project: kernel
ms.assetid: 1E7BB805-1A91-4DA6-A7E9-E60DD8D4AAF3
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlLongPtrToUInt8
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
req.alt-api: RtlLongPtrToUInt8
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
req.iface: 
---

# RtlLongPtrToUInt8 function



## -description
<p>Converts a value of type <b>LONG_PTR</b> to a value of type <b>UINT8</b>.</p>


## -syntax

````
NTSTATUS RtlLongPtrToUInt8(
  _In_  LONG_PTR lOperand,
  _Out_ UINT8    *pui8Result
);
````


## -parameters
<dl>

### -param <i>lOperand</i> [in]

<dd>
<p>The value to be converted.</p>
</dd>

### -param <i>pui8Result</i> [out]

<dd>
<p>A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.</p>
</dd>
</dl>

## -remarks
<p>This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.</p>

<p>This function uses the following alternate name:</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntintsafe.h</dt>
</dl>
</td>
</tr>
</table>