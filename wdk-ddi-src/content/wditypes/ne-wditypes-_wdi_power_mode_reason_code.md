---
UID: NE:wditypes._WDI_POWER_MODE_REASON_CODE
title: "_WDI_POWER_MODE_REASON_CODE"
author: windows-driver-content
description: The WDI_POWER_MODE_REASON_CODE enumeration defines the reasons for entering the Power Save state.
old-location: netvista\wdi_power_mode_reason_code.htm
old-project: netvista
ms.assetid: F9FAA622-A844-4D9F-A0E6-D919C1FAD3AB
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WDI_POWER_MODE_REASON_CODE_COMPLIANT_P2P_DEVICE, wditypes/WDI_POWER_MODE_REASON_CODE_NO_CHANGE, _WDI_POWER_MODE_REASON_CODE, WDI_POWER_MODE_REASON_CODE_COMPLIANT_AP, WDI_POWER_MODE_REASON_CODE, WDI_POWER_MODE_REASON_CODE_NO_CHANGE, WDI_POWER_MODE_REASON_CODE_LEGACY_P2P_DEVICE, netvista.wifi_power_mode_reason_code, wditypes/WDI_POWER_MODE_REASON_CODE_OTHERS, wditypes/WDI_POWER_MODE_REASON_CODE_NONCOMPLIANT_AP, WDI_POWER_MODE_REASON_CODE enumeration [Network Drivers Starting with Windows Vista], wditypes/WDI_POWER_MODE_REASON_CODE_LEGACY_P2P_DEVICE, WDI_POWER_MODE_REASON_CODE_NONCOMPLIANT_AP, wditypes/WDI_POWER_MODE_REASON_CODE_COMPLIANT_AP, wditypes/WDI_POWER_MODE_REASON_CODE_COMPLIANT_P2P_DEVICE, netvista.wdi_power_mode_reason_code, WDI_POWER_MODE_REASON_CODE_OTHERS, wditypes/WDI_POWER_MODE_REASON_CODE
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
-	WDI_POWER_MODE_REASON_CODE
product: Windows
targetos: Windows
req.typenames: WDI_POWER_MODE_REASON_CODE
req.product: Windows 10 or later.
---

# _WDI_POWER_MODE_REASON_CODE Enumeration
The WDI_POWER_MODE_REASON_CODE enumeration defines the reasons for entering the Power Save state.

## Syntax
````
typedef enum _WDI_POWER_MODE_REASON_CODE { 
  WDI_POWER_MODE_REASON_CODE_NO_CHANGE             = 0,
  WDI_POWER_MODE_REASON_CODE_NONCOMPLIANT_AP       = 1,
  WDI_POWER_MODE_REASON_CODE_LEGACY_P2P_DEVICE     = 2,
  WDI_POWER_MODE_REASON_CODE_COMPLIANT_AP          = 3,
  WDI_POWER_MODE_REASON_CODE_COMPLIANT_P2P_DEVICE  = 4,
  WDI_POWER_MODE_REASON_CODE_OTHERS                = 5
} WDI_POWER_MODE_REASON_CODE;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_POWER_MODE_REASON_CODE_COMPLIANT_AP</td>
                    <td>AP is compliant.</td>
                </tr>
            
                <tr>
                    <td>WDI_POWER_MODE_REASON_CODE_COMPLIANT_P2P_DEVICE</td>
                    <td>All connected WFD device can do PSM.</td>
                </tr>
            
                <tr>
                    <td>WDI_POWER_MODE_REASON_CODE_LEGACY_P2P_DEVICE</td>
                    <td>WFD device is legacy.</td>
                </tr>
            
                <tr>
                    <td>WDI_POWER_MODE_REASON_CODE_NO_CHANGE</td>
                    <td>Device is initially in this state and has not changed since.</td>
                </tr>
            
                <tr>
                    <td>WDI_POWER_MODE_REASON_CODE_NONCOMPLANT_AP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WDI_POWER_MODE_REASON_CODE_OTHERS</td>
                    <td>Other reason.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |