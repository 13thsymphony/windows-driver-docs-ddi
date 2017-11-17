---
UID: NS.ks.PKSQUALITY
title: PKSQUALITY
author: windows-driver-content
description: The KSQUALITY structure is used to report QM problems in both kernel and user mode to their respective quality managers.
old-location: stream\ksquality.htm
ms.assetid: 36caaea9-2354-4ed8-9649-5eb102def8d5
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: stream
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSQUALITY
req.alt-loc: ks.h
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
ms.keywords: PKSQUALITY, KSQUALITY, *PKSQUALITY
req.iface: 
---

# PKSQUALITY structure



## -description
<p>The KSQUALITY structure is used to report QM problems in both kernel and user mode to their respective quality managers.</p>


## -syntax

````
typedef struct {
  PVOID    Context;
  ULONG    Proportion;
  LONGLONG DeltaTime;
} KSQUALITY, *PKSQUALITY;
````


## -struct-fields
<dl>

### -field <b>Context</b>

<dd>
<p>Specifies a context parameter that was originally passed to the connection.</p>
</dd>

### -field <b>Proportion</b>

<dd>
<p>Indicates the percentage of frames currently being received that are actually being used. This is expressed in units of one-tenth of a percent, where 1000 is optimal.</p>
</dd>

### -field <b>DeltaTime</b>

<dd>
<p>Indicates the delta in native units (as indicated by the Interface) from optimal time at which the frames are being delivered, where a positive number means too late, and a negative number means too early. Zero indicates a correct delta.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>