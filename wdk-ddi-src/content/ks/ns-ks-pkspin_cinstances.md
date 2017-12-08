---
UID: NS.KS.PKSPIN_CINSTANCES
title: PKSPIN_CINSTANCES
author: windows-driver-content
description: .
old-location: stream\kspin_cinstances.htm
old-project: stream
ms.assetid: 90C861C3-26E0-43C0-A4CA-FD5491995DAB
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSPIN_CINSTANCES, *PKSPIN_CINSTANCES, KSPIN_CINSTANCES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPIN_CINSTANCES
req.alt-loc: Ks.h
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

# PKSPIN_CINSTANCES structure



## -description



## -syntax

````
typedef struct {
  ULONG PossibleCount;
  ULONG CurrentCount;
} KSPIN_CINSTANCES, *PKSPIN_CINSTANCES;
````


## -struct-fields

### -field PossibleCount

Specifies the maximum number of pins the pin factory can instantiate on the filter, or KSINTANCE_INDETERMINATE if there is no maximum.

### -field CurrentCount

Specifies the current number of pins the pin factory has instantiated on the filter.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h</dt>
</dl>
</td>
</tr>
</table>