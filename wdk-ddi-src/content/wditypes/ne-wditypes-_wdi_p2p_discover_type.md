---
UID: NE:wditypes._WDI_P2P_DISCOVER_TYPE
title: _WDI_P2P_DISCOVER_TYPE
author: windows-driver-content
description: The WDI_P2P_DISCOVER_TYPE enumeration defines the Wi-Fi Direct discovery types.
old-location: netvista\wdi_p2p_discover_type.htm
old-project: netvista
ms.assetid: AE9910F7-A3B8-4C13-A5DC-7B9600C8C873
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDI_P2P_DISCOVER_TYPE, WDI_P2P_DISCOVER_TYPE
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
req.alt-api: WDI_P2P_DISCOVER_TYPE
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
req.typenames: WDI_P2P_DISCOVER_TYPE
req.product: Windows 10 or later.
---

# _WDI_P2P_DISCOVER_TYPE enumeration



## -description
The WDI_P2P_DISCOVER_TYPE enumeration defines the Wi-Fi Direct discovery types.



## -syntax

````
typedef enum _WDI_P2P_DISCOVER_TYPE { 
  WDI_P2P_DISCOVER_TYPE_SCAN_ONLY             = 1,
  WDI_P2P_DISCOVER_TYPE_FIND_ONLY             = 2,
  WDI_P2P_DISCOVER_TYPE_AUTO                  = 3,
  WDI_P2P_DISCOVER_TYPE_SCAN_SOCIAL_CHANNELS  = 4
} WDI_P2P_DISCOVER_TYPE;
````


## -enum-fields

### -field WDI_P2P_DISCOVER_TYPE_SCAN_ONLY

Device discovery occurs only during the scan phase. Adapter should scan each channel at least once every 250 milliseconds.


### -field WDI_P2P_DISCOVER_TYPE_FIND_ONLY

Device discovery occurs only during the find phase.


### -field WDI_P2P_DISCOVER_TYPE_AUTO

Device discovery is determined by the port.


### -field WDI_P2P_DISCOVER_TYPE_SCAN_SOCIAL_CHANNELS

Port must perform device discovery by scanning only Wi-Fi Direct social channels. In this setting, the adapter should scan each social channel at least once every 250 milliseconds.


## -remarks
