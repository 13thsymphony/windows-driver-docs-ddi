---
UID: NE:dot11wdi._WDI_RX_THROTTLE_LEVEL
title: "_WDI_RX_THROTTLE_LEVEL"
author: windows-driver-content
description: The WDI_RX_THROTTLE_LEVEL enumeration defines the RX throttle level. The interpretation and implementation mechanisms of these throttle levels are defined by the independent hardware vendor (IHV).
old-location: netvista\wdi_rx_throttle_level.htm
old-project: netvista
ms.assetid: 637c0892-8d73-45b7-b679-ff3a0ba78a9c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: WDI_RX_THROTTLE_LEVEL, WDI_RX_THROTTLE_LEVEL enumeration [Network Drivers Starting with Windows Vista], WDI_RxThrottleLevelAggressive, WDI_RxThrottleLevelMedium, WDI_RxThrottleLevelNone, _WDI_RX_THROTTLE_LEVEL, dot11wdi/WDI_RX_THROTTLE_LEVEL, dot11wdi/WDI_RxThrottleLevelAggressive, dot11wdi/WDI_RxThrottleLevelMedium, dot11wdi/WDI_RxThrottleLevelNone, netvista.wdi_rx_throttle_level, netvista.wifi_rx_throttle_level
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
-	dot11wdi.h
api_name:
-	WDI_RX_THROTTLE_LEVEL
product: Windows
targetos: Windows
req.typenames: WDI_RX_THROTTLE_LEVEL
---

# _WDI_RX_THROTTLE_LEVEL Enumeration
The WDI_RX_THROTTLE_LEVEL enumeration defines the RX throttle level. The interpretation and implementation mechanisms of these throttle levels are defined by the independent hardware vendor (IHV).

## Syntax
````
typedef enum _WDI_RX_THROTTLE_LEVEL { 
  WDI_RxThrottleLevelNone        = 0x0,
  WDI_RxThrottleLevelMedium      = 0x1,
  WDI_RxThrottleLevelAggressive  = 0x2
} WDI_RX_THROTTLE_LEVEL;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_RxThrottleLevelAggressive</td>
                    <td>Aggressive throttling.</td>
                </tr>
            
                <tr>
                    <td>WDI_RxThrottleLevelMax</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WDI_RxThrottleLevelMedium</td>
                    <td>Medium throttling.</td>
                </tr>
            
                <tr>
                    <td>WDI_RxThrottleLevelNone</td>
                    <td>No throttling.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |