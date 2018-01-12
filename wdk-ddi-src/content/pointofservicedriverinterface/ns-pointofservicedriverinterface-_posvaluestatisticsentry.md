---
UID: NS:pointofservicedriverinterface._PosValueStatisticsEntry
title: _PosValueStatisticsEntry
author: windows-driver-content
description: This structure contains the value of a statistic.
old-location: pos\posvaluestatisticsentry.htm
old-project: pos
ms.assetid: e6627d5f-5905-479e-b968-6914491231b1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _PosValueStatisticsEntry, PosValueStatisticsEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PosValueStatisticsEntry
req.alt-loc: PointOfServiceDriverInterface.h
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
req.typenames: PosValueStatisticsEntry
---

# _PosValueStatisticsEntry structure



## -description
This structure contains the value of a statistic.



## -syntax

````
typedef struct _PosValueStatisticsEntry {
  wchar_t       EntryName[STATISTICS_STRING_SIZE];
  volatile LONG Value;
} PosValueStatisticsEntry;
````


## -struct-fields

### -field EntryName

Indicates the NULL-terminated statistic name (for example, <i>GoodScanCount</i> or <i>BadScanCount</i>).


### -field Value

Indicates the current statistic value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>PointOfServiceDriverInterface.h (include PointOfServiceDriverInterface.h)</dt>
</dl>
</td>
</tr>
</table>