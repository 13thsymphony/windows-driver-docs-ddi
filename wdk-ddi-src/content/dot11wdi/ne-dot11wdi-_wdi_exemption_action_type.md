---
UID: NE:dot11wdi._WDI_EXEMPTION_ACTION_TYPE
title: _WDI_EXEMPTION_ACTION_TYPE
author: windows-driver-content
description: The WDI_EXEMPTION_ACTION_TYPE enumeration defines the exemption types.
old-location: netvista\wdi_exemption_action_type.htm
old-project: netvista
ms.assetid: 46640961-828c-411b-b1b9-bcceb04bdf17
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _WDI_EXEMPTION_ACTION_TYPE, WDI_EXEMPTION_ACTION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_EXEMPTION_ACTION_TYPE
req.alt-loc: dot11wdi.h
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
req.typenames: WDI_EXEMPTION_ACTION_TYPE
---

# _WDI_EXEMPTION_ACTION_TYPE enumeration



## -description
The WDI_EXEMPTION_ACTION_TYPE enumeration defines the exemption types.



## -syntax

````
typedef enum _WDI_EXEMPTION_ACTION_TYPE { 
  WDI_EXEMPT_NO_EXEMPTION                    = 0,
  WDI_EXEMPT_ALWAYS                          = 1,
  WDI_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE  = 2
} WDI_EXEMPTION_ACTION_TYPE;
````


## -enum-fields

### -field WDI_EXEMPT_NO_EXEMPTION

Packets are not exempt from any cipher operations performed by the port.


### -field WDI_EXEMPT_ALWAYS

On send, packets are exempt from cipher operations and are transmitted unencrypted. On receive, the received packet is discarded if the Protected Frame subfield of the Frame Control field in the 802.11 MAC header is set to 1.


### -field WDI_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE

On send, packets are exempt from cipher operations if there is no key-mapping key for the packet's destination MAC address. On receive, the received packet is discarded if a key-mapping key for the source MAC address is available and the Protected Frame subfield of the Frame Control field in the 802.11 MAC header is set to 0.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dot11wdi.h</dt>
</dl>
</td>
</tr>
</table>