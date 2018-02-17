---
UID: NE:wditypes._WDI_SCAN_TYPE
title: "_WDI_SCAN_TYPE"
author: windows-driver-content
description: The WDI_SCAN_TYPE enumeration defines the scan types.
old-location: netvista\wdi_scan_type.htm
old-project: netvista
ms.assetid: DF4ECD03-2C2F-44B3-82BE-E57B333AF069
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.wdi_scan_type, netvista.wifi_scan_type, wditypes/WDI_SCAN_TYPE, WDI_SCAN_TYPE, wditypes/WDI_SCAN_TYPE_AUTO, _WDI_SCAN_TYPE, WDI_SCAN_TYPE_ACTIVE_ONLY, wditypes/WDI_SCAN_TYPE_ACTIVE_ONLY, WDI_SCAN_TYPE enumeration [Device and Driver Installation], WDI_SCAN_TYPE_AUTO, WDI_SCAN_TYPE_PASSIVE_ONLY, wditypes/WDI_SCAN_TYPE_PASSIVE_ONLY
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wditypes.hpp
apiname:
-	WDI_SCAN_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_SCAN_TYPE
req.product: Windows 10 or later.
---

# _WDI_SCAN_TYPE Enumeration
The WDI_SCAN_TYPE enumeration defines the scan types.

## Syntax
````
typedef enum _WDI_SCAN_TYPE { 
  WDI_SCAN_TYPE_ACTIVE_ONLY   = 1,
  WDI_SCAN_TYPE_PASSIVE_ONLY  = 2,
  WDI_SCAN_TYPE_AUTO          = 3
} WDI_SCAN_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_SCAN_TYPE_ACTIVE_ONLY</td>
                    <td>The port should transmit a probe request on the channels that it scans. Even for active scans, the port must follow regulatory restrictions on the channel and must not scan on channels that would need a passive scan.</td>
                </tr>
            
                <tr>
                    <td>WDI_SCAN_TYPE_AUTO</td>
                    <td>The port can perform an active or passive can or can use a combination of both scan types. It should prefer using Active scans when possible. This is the default scan type setting.</td>
                </tr>
            
                <tr>
                    <td>WDI_SCAN_TYPE_MAX_VALUE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WDI_SCAN_TYPE_PASSIVE_ONLY</td>
                    <td>The port should not transmit a probe request on the channels that it scans.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |