---
UID : NE:wditypes._WDI_P2P_SCAN_TYPE
title : "_WDI_P2P_SCAN_TYPE"
author : windows-driver-content
description : The WDI_P2P_SCAN_TYPE enumeration defines the Wi-Fi Direct scan types.
old-location : netvista\wdi_p2p_scan_type.htm
old-project : netvista
ms.assetid : 717847D7-D7D9-4FEE-B3DC-14B0404FA937
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wditypes/WDI_P2P_SCAN_TYPE_ACTIVE, WDI_P2P_SCAN_TYPE_PASSIVE, WDI_P2P_SCAN_TYPE, wditypes/WDI_P2P_SCAN_TYPE, WDI_P2P_SCAN_TYPE_AUTO, netvista.wifi_p2p_scan_type, _WDI_P2P_SCAN_TYPE, wditypes/WDI_P2P_SCAN_TYPE_AUTO, WDI_P2P_SCAN_TYPE enumeration [Device and Driver Installation], wditypes/WDI_P2P_SCAN_TYPE_PASSIVE, netvista.wdi_p2p_scan_type, WDI_P2P_SCAN_TYPE_ACTIVE
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
req.typenames : WDI_P2P_SCAN_TYPE
req.product : Windows 10 or later.
---

# _WDI_P2P_SCAN_TYPE Enumeration
The WDI_P2P_SCAN_TYPE enumeration defines the Wi-Fi Direct scan types.

## Syntax
````
typedef enum _WDI_P2P_SCAN_TYPE { 
  WDI_P2P_SCAN_TYPE_ACTIVE   = 1,
  WDI_P2P_SCAN_TYPE_PASSIVE  = 2,
  WDI_P2P_SCAN_TYPE_AUTO     = 3
} WDI_P2P_SCAN_TYPE;
````

## Constants

<table>

<tr>
<td>WDI_P2P_SCAN_TYPE_ACTIVE</td>
<td>Use active scanning during device discovery. Even for active scans, the port must follow regulatory restrictions on the channel and must not scan on channels that would need a passive scan.</td>
</tr>

<tr>
<td>WDI_P2P_SCAN_TYPE_AUTO</td>
<td>Adapter determines scan type during device discovery. It should prefer using Active scans when possible. This is the default scan type setting.</td>
</tr>

<tr>
<td>WDI_P2P_SCAN_TYPE_MAX_VALUE</td>
<td></td>
</tr>

<tr>
<td>WDI_P2P_SCAN_TYPE_PASSIVE</td>
<td>Use passive scanning during device discovery.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |