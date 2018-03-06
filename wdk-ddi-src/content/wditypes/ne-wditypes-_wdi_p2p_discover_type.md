---
UID: NE:wditypes._WDI_P2P_DISCOVER_TYPE
title: "_WDI_P2P_DISCOVER_TYPE"
author: windows-driver-content
description: The WDI_P2P_DISCOVER_TYPE enumeration defines the Wi-Fi Direct discovery types.
old-location: netvista\wdi_p2p_discover_type.htm
old-project: netvista
ms.assetid: AE9910F7-A3B8-4C13-A5DC-7B9600C8C873
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDI_P2P_DISCOVER_TYPE, WDI_P2P_DISCOVER_TYPE enumeration [Device and Driver Installation], WDI_P2P_DISCOVER_TYPE_AUTO, WDI_P2P_DISCOVER_TYPE_FIND_ONLY, WDI_P2P_DISCOVER_TYPE_SCAN_ONLY, WDI_P2P_DISCOVER_TYPE_SCAN_SOCIAL_CHANNELS, _WDI_P2P_DISCOVER_TYPE, netvista.wdi_p2p_discover_type, netvista.wifi_p2p_discover_type, wditypes/WDI_P2P_DISCOVER_TYPE, wditypes/WDI_P2P_DISCOVER_TYPE_AUTO, wditypes/WDI_P2P_DISCOVER_TYPE_FIND_ONLY, wditypes/WDI_P2P_DISCOVER_TYPE_SCAN_ONLY, wditypes/WDI_P2P_DISCOVER_TYPE_SCAN_SOCIAL_CHANNELS
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wditypes.hpp
api_name:
-	WDI_P2P_DISCOVER_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_P2P_DISCOVER_TYPE
req.product: Windows 10 or later.
---

# _WDI_P2P_DISCOVER_TYPE Enumeration
The WDI_P2P_DISCOVER_TYPE enumeration defines the Wi-Fi Direct discovery types.

## Syntax
````
typedef enum _WDI_P2P_DISCOVER_TYPE { 
  WDI_P2P_DISCOVER_TYPE_SCAN_ONLY             = 1,
  WDI_P2P_DISCOVER_TYPE_FIND_ONLY             = 2,
  WDI_P2P_DISCOVER_TYPE_AUTO                  = 3,
  WDI_P2P_DISCOVER_TYPE_SCAN_SOCIAL_CHANNELS  = 4
} WDI_P2P_DISCOVER_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_P2P_DISCOVER_TYPE_AUTO</td>
                    <td>Device discovery is determined by the port.</td>
                </tr>
            
                <tr>
                    <td>WDI_P2P_DISCOVER_TYPE_FIND_ONLY</td>
                    <td>Device discovery occurs only during the find phase.</td>
                </tr>
            
                <tr>
                    <td>WDI_P2P_DISCOVER_TYPE_MAX_VALUE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WDI_P2P_DISCOVER_TYPE_SCAN_ONLY</td>
                    <td>Device discovery occurs only during the scan phase. Adapter should scan each channel at least once every 250 milliseconds.</td>
                </tr>
            
                <tr>
                    <td>WDI_P2P_DISCOVER_TYPE_SCAN_SOCIAL_CHANNELS</td>
                    <td>Port must perform device discovery by scanning only Wi-Fi Direct social channels. In this setting, the adapter should scan each social channel at least once every 250 milliseconds.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |