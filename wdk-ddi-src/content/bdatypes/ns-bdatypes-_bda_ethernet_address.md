---
UID: NS:bdatypes._BDA_ETHERNET_ADDRESS
title: _BDA_ETHERNET_ADDRESS
author: windows-driver-content
description: .
old-location: stream\bda_ethernet_address.htm
old-project: stream
ms.assetid: F4B9A413-7FB5-4CA3-9731-A143CB0D7346
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _BDA_ETHERNET_ADDRESS, *PBDA_ETHERNET_ADDRESS, BDA_ETHERNET_ADDRESS
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
req.alt-api: BDA_ETHERNET_ADDRESS
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
req.typenames: *PBDA_ETHERNET_ADDRESS, BDA_ETHERNET_ADDRESS
---

# _BDA_ETHERNET_ADDRESS structure



## -description




## -syntax

````
typedef struct _BDA_ETHERNET_ADDRESS {
  BYTE rgbAddress[6];
} BDA_ETHERNET_ADDRESS, *PBDA_ETHERNET_ADDRESS;
````


## -struct-fields

### -field rgbAddress


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