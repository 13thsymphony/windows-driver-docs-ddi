---
UID: NS.BDATYPES._BDA_SIGNAL_TIMEOUTS
title: _BDA_SIGNAL_TIMEOUTS
author: windows-driver-content
description: .
old-location: stream\bda_signal_timeouts.htm
old-project: stream
ms.assetid: CFEF848D-8268-4FFC-A629-D122021D8411
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _BDA_SIGNAL_TIMEOUTS, BDA_SIGNAL_TIMEOUTS, *PBDA_SIGNAL_TIMEOUTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BDA_SIGNAL_TIMEOUTS
req.alt-loc: Bdatypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _BDA_SIGNAL_TIMEOUTS structure



## -description



## -syntax

````
typedef struct _BDA_SIGNAL_TIMEOUTS {
  ULONG ulCarrierTimeoutMs;
  ULONG ulScanningTimeoutMs;
  ULONG ulTuningTimeoutMs;
} BDA_SIGNAL_TIMEOUTS, *PBDA_SIGNAL_TIMEOUTS;
````


## -struct-fields

### -field ulCarrierTimeoutMs


### -field ulScanningTimeoutMs


### -field ulTuningTimeoutMs


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Bdatypes.h</dt>
</dl>
</td>
</tr>
</table>