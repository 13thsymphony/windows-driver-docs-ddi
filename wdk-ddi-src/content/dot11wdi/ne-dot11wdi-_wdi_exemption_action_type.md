---
UID : NE:dot11wdi._WDI_EXEMPTION_ACTION_TYPE
title : "_WDI_EXEMPTION_ACTION_TYPE"
author : windows-driver-content
description : The WDI_EXEMPTION_ACTION_TYPE enumeration defines the exemption types.
old-location : netvista\wdi_exemption_action_type.htm
old-project : netvista
ms.assetid : 46640961-828c-411b-b1b9-bcceb04bdf17
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.wdi_exemption_action_type, dot11wdi/WDI_EXEMPT_ALWAYS, WDI_EXEMPT_ALWAYS, _WDI_EXEMPTION_ACTION_TYPE, WDI_EXEMPT_NO_EXEMPTION, dot11wdi/WDI_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE, dot11wdi/WDI_EXEMPT_NO_EXEMPTION, WDI_EXEMPTION_ACTION_TYPE, WDI_EXEMPTION_ACTION_TYPE enumeration [Network Drivers Starting with Windows Vista], netvista.wifi_exemption_action_type, WDI_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE, dot11wdi/WDI_EXEMPTION_ACTION_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : dot11wdi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDI_EXEMPTION_ACTION_TYPE
---

# _WDI_EXEMPTION_ACTION_TYPE Enumeration
The WDI_EXEMPTION_ACTION_TYPE enumeration defines the exemption types.

## Syntax
````
typedef enum _WDI_EXEMPTION_ACTION_TYPE { 
  WDI_EXEMPT_NO_EXEMPTION                    = 0,
  WDI_EXEMPT_ALWAYS                          = 1,
  WDI_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE  = 2
} WDI_EXEMPTION_ACTION_TYPE;
````

## Constants

<table>

<tr>
<td>WDI_EXEMPT_ALWAYS</td>
<td>On send, packets are exempt from cipher operations and are transmitted unencrypted. On receive, the received packet is discarded if the Protected Frame subfield of the Frame Control field in the 802.11 MAC header is set to 1.</td>
</tr>

<tr>
<td>WDI_EXEMPT_NO_EXEMPTION</td>
<td>Packets are not exempt from any cipher operations performed by the port.</td>
</tr>

<tr>
<td>WDI_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE</td>
<td>On send, packets are exempt from cipher operations if there is no key-mapping key for the packet's destination MAC address. On receive, the received packet is discarded if a key-mapping key for the source MAC address is available and the Protected Frame subfield of the Frame Control field in the 802.11 MAC header is set to 0.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |