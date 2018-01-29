---
UID : NE:wditypes._WDI_P2P_GO_INTERNAL_RESET_POLICY
title : _WDI_P2P_GO_INTERNAL_RESET_POLICY
author : windows-driver-content
description : The WDI_P2P_GO_INTERNAL_RESET_POLICY enumeration defines the Wi-Fi Direct Group Owner internal reset policies.
old-location : netvista\wdi_p2p_go_internal_reset_policy.htm
old-project : netvista
ms.assetid : 7932A2BB-DD6D-4DF7-BDF9-4E476B06B0B5
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : WDI_P2P_GO_INTERNAL_RESET_POLICY, WDI_P2P_GO_INTERNAL_RESET_POLICY_ALLOW_CHANNEL_OPTIMIZATION, WDI_P2P_GO_INTERNAL_RESET_POLICY_USE_LAST_CHANNEL, netvista.wifi_p2p_go_internal_reset_policy, _WDI_P2P_GO_INTERNAL_RESET_POLICY, wditypes/WDI_P2P_GO_INTERNAL_RESET_POLICY, wditypes/WDI_P2P_GO_INTERNAL_RESET_POLICY_ALLOW_CHANNEL_OPTIMIZATION, WDI_P2P_GO_INTERNAL_RESET_POLICY enumeration [Device and Driver Installation], netvista.wdi_p2p_go_internal_reset_policy, wditypes/WDI_P2P_GO_INTERNAL_RESET_POLICY_USE_LAST_CHANNEL
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wditypes.hpp
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
req.typenames : WDI_P2P_GO_INTERNAL_RESET_POLICY
req.product : Windows 10 or later.
---

# _WDI_P2P_GO_INTERNAL_RESET_POLICY Enumeration
The WDI_P2P_GO_INTERNAL_RESET_POLICY enumeration defines the Wi-Fi Direct Group Owner internal reset policies.

## Syntax
````
typedef enum _WDI_P2P_GO_INTERNAL_RESET_POLICY { 
  WDI_P2P_GO_INTERNAL_RESET_POLICY_USE_LAST_CHANNEL            = 1,
  WDI_P2P_GO_INTERNAL_RESET_POLICY_ALLOW_CHANNEL_OPTIMIZATION  = 2
} WDI_P2P_GO_INTERNAL_RESET_POLICY;
````

## Constants

<table>

<tr>
<td>WDI_P2P_GO_INTERNAL_RESET_POLICY_ALLOW_CHANNEL_OPTIMIZATION</td>
<td>If an internal-to-firmware Group Owner reset is performed, firmware may freely decide its new operating channel. For example, firmware may choose to minimize channel switching by adopting station port channel. If there is no optimization to be done, fall back to selecting previous operating channel.</td>
</tr>

<tr>
<td>WDI_P2P_GO_INTERNAL_RESET_POLICY_MAX</td>
<td></td>
</tr>

<tr>
<td>WDI_P2P_GO_INTERNAL_RESET_POLICY_USE_LAST_CHANNEL</td>
<td>If an internal-to-firmware Group Owner reset is performed, post-reset Group Owner must operate on the same operating channel as before the internal reset operation.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wditypes.hpp |