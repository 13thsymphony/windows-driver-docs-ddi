---
UID: NS.BDATYPES._BDA_DISEQC_RESPONSE
title: _BDA_DISEQC_RESPONSE
author: windows-driver-content
description: .
old-location: stream\bda_diseqc_response.htm
old-project: stream
ms.assetid: 724FD17B-D12B-423D-AA0E-93D9D31DC93E
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _BDA_DISEQC_RESPONSE, *PBDA_DISEQC_RESPONSE, BDA_DISEQC_RESPONSE
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
req.alt-api: BDA_DISEQC_RESPONSE
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

# _BDA_DISEQC_RESPONSE structure



## -description




## -syntax

````
typedef struct _BDA_DISEQC_RESPONSE {
  ULONG ulRequestId;
  ULONG ulPacketLength;
  BYTE  argbPacketData[8];
} BDA_DISEQC_RESPONSE, *PBDA_DISEQC_RESPONSE;
````


## -struct-fields

### -field ulRequestId


### -field ulPacketLength


### -field argbPacketData


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