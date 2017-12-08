---
UID: NE.wditypes._WDI_P2P_SCAN_TYPE
title: _WDI_P2P_SCAN_TYPE
author: windows-driver-content
description: The WDI_P2P_SCAN_TYPE enumeration defines the Wi-Fi Direct scan types.
old-location: netvista\wdi_p2p_scan_type.htm
old-project: netvista
ms.assetid: 717847D7-D7D9-4FEE-B3DC-14B0404FA937
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WDI_P2P_SCAN_TYPE, WDI_P2P_SCAN_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_P2P_SCAN_TYPE
req.alt-loc: wditypes.hpp
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
req.product: Windows 10 or later.
---

# _WDI_P2P_SCAN_TYPE enumeration



## -description
The WDI_P2P_SCAN_TYPE enumeration defines the Wi-Fi Direct scan types.


## -syntax

````
typedef enum _WDI_P2P_SCAN_TYPE { 
  WDI_P2P_SCAN_TYPE_ACTIVE   = 1,
  WDI_P2P_SCAN_TYPE_PASSIVE  = 2,
  WDI_P2P_SCAN_TYPE_AUTO     = 3
} WDI_P2P_SCAN_TYPE;
````


## -enum-fields

### -field WDI_P2P_SCAN_TYPE_ACTIVE

Use active scanning during device discovery. Even for active scans, the port must follow regulatory restrictions on the channel and must not scan on channels that would need a passive scan.

### -field WDI_P2P_SCAN_TYPE_PASSIVE

Use passive scanning during device discovery.

### -field WDI_P2P_SCAN_TYPE_AUTO

Adapter determines scan type during device discovery. It should prefer using Active scans when possible. This is the default scan type setting.

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
<dt>Wditypes.hpp</dt>
</dl>
</td>
</tr>
</table>