---
UID: NS:bdatypes._BDA_ETHERNET_ADDRESS_LIST
title: _BDA_ETHERNET_ADDRESS_LIST
author: windows-driver-content
description: .
old-location: stream\bda_ethernet_address_list.htm
old-project: stream
ms.assetid: 2985A0EC-4B5F-43FA-A2E9-487877A3C9A0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _BDA_ETHERNET_ADDRESS_LIST, BDA_ETHERNET_ADDRESS_LIST, *PBDA_ETHERNET_ADDRESS_LIST
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
req.alt-api: BDA_ETHERNET_ADDRESS_LIST
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
req.typenames: BDA_ETHERNET_ADDRESS_LIST, *PBDA_ETHERNET_ADDRESS_LIST
---

# _BDA_ETHERNET_ADDRESS_LIST structure



## -description




## -syntax

````
typedef struct _BDA_ETHERNET_ADDRESS_LIST {
  ULONG                ulcAddresses;
  BDA_ETHERNET_ADDRESS rgAddressl[MIN_DIMENSION];
} BDA_ETHERNET_ADDRESS_LIST, *PBDA_ETHERNET_ADDRESS_LIST;
````


## -struct-fields

### -field ulcAddresses


### -field rgAddressl


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