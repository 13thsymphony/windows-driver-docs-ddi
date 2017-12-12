---
UID: NS.BDATYPES._BDA_GDDS_DATA
title: _BDA_GDDS_DATA
author: windows-driver-content
description: .
old-location: stream\bda_gdds_data.htm
old-project: stream
ms.assetid: 2BBF14E3-8E1A-42AF-9C26-7F886FD2B945
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _BDA_GDDS_DATA, *P_BDA_GDDS_DATA, BDA_GDDS_DATA
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
req.alt-api: BDA_GDDS_DATA
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

# _BDA_GDDS_DATA structure



## -description




## -syntax

````
typedef struct _BDA_GDDS_DATA {
  PBDARESULT lResult;
  ULONG      ulDataLength;
  ULONG      ulPercentageProgress;
  ULONG      argbData[MIN_DIMENSION];
} BDA_GDDS_DATA, *P_BDA_GDDS_DATA;
````


## -struct-fields

### -field lResult


### -field ulDataLength


### -field ulPercentageProgress


### -field argbData


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