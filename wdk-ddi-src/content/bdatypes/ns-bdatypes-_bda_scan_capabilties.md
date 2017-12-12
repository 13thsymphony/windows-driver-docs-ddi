---
UID: NS.BDATYPES._BDA_SCAN_CAPABILTIES
title: _BDA_SCAN_CAPABILTIES
author: windows-driver-content
description: .
old-location: stream\bda_scan_capabilties.htm
old-project: stream
ms.assetid: AB97C5AC-E5B8-4C2B-ADA1-73E27E4B81D5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _BDA_SCAN_CAPABILTIES, *PBDA_SCAN_CAPABILTIES, BDA_SCAN_CAPABILTIES
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
req.alt-api: BDA_SCAN_CAPABILTIES
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

# _BDA_SCAN_CAPABILTIES structure



## -description




## -syntax

````
typedef struct _BDA_SCAN_CAPABILTIES {
  PBDARESULT lResult;
  UINT64     ul64AnalogStandardsSupported;
} BDA_SCAN_CAPABILTIES, *PBDA_SCAN_CAPABILTIES;
````


## -struct-fields

### -field lResult


### -field ul64AnalogStandardsSupported


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