---
UID: NS.ksproxy.OPTIMAL_WEIGHT_TOTALS
title: OPTIMAL_WEIGHT_TOTALS
author: windows-driver-content
description: .
old-location: stream\optimal_weight_totals.htm
old-project: stream
ms.assetid: 56D97D0F-1934-4834-99A7-8A745A3E6757
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: OPTIMAL_WEIGHT_TOTALS, OPTIMAL_WEIGHT_TOTALS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksproxy.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OPTIMAL_WEIGHT_TOTALS
req.alt-loc: Ksproxy.h
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

# OPTIMAL_WEIGHT_TOTALS structure



## -description
<p></p>


## -syntax

````
typedef struct {
  LONGLONG MinTotalNominator;
  LONGLONG MaxTotalNominator;
  LONGLONG TotalDenominator;
} OPTIMAL_WEIGHT_TOTALS;
````


## -struct-fields
<dl>

### -field <b>MinTotalNominator</b>

<dd></dd>

### -field <b>MaxTotalNominator</b>

<dd></dd>

### -field <b>TotalDenominator</b>

<dd></dd>
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
<dt>Ksproxy.h</dt>
</dl>
</td>
</tr>
</table>