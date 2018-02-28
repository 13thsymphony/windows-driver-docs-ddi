---
UID: NE:wditypes._WDI_PHY_TYPE
title: "_WDI_PHY_TYPE"
author: windows-driver-content
description: The WDI_PHY_TYPE enumeration defines the PHY types.
old-location: netvista\wdi_phy_type.htm
old-project: netvista
ms.assetid: BDA90056-6DAA-4FC8-82EC-3062087E02C4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WDI_PHY_TYPE, WDI_PHY_TYPE enumeration [Network Drivers Starting with Windows Vista], WDI_PHY_TYPE_ANY, WDI_PHY_TYPE_DMG, WDI_PHY_TYPE_DSSS, WDI_PHY_TYPE_ERP, WDI_PHY_TYPE_FHSS, WDI_PHY_TYPE_HRDSSS, WDI_PHY_TYPE_HT, WDI_PHY_TYPE_IHV_END, WDI_PHY_TYPE_IHV_START, WDI_PHY_TYPE_IRBASEBAND, WDI_PHY_TYPE_OFDM, WDI_PHY_TYPE_UNKNOWN, WDI_PHY_TYPE_VHT, _WDI_PHY_TYPE, netvista.wdi_phy_type, netvista.wifi_phy_type, wditypes/WDI_PHY_TYPE, wditypes/WDI_PHY_TYPE_ANY, wditypes/WDI_PHY_TYPE_DMG, wditypes/WDI_PHY_TYPE_DSSS, wditypes/WDI_PHY_TYPE_ERP, wditypes/WDI_PHY_TYPE_FHSS, wditypes/WDI_PHY_TYPE_HRDSSS, wditypes/WDI_PHY_TYPE_HT, wditypes/WDI_PHY_TYPE_IHV_END, wditypes/WDI_PHY_TYPE_IHV_START, wditypes/WDI_PHY_TYPE_IRBASEBAND, wditypes/WDI_PHY_TYPE_OFDM, wditypes/WDI_PHY_TYPE_UNKNOWN, wditypes/WDI_PHY_TYPE_VHT
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
-	WDI_PHY_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_PHY_TYPE
req.product: Windows 10 or later.
---

# _WDI_PHY_TYPE Enumeration
The WDI_PHY_TYPE enumeration defines the PHY types.

## Syntax
````
typedef enum _WDI_PHY_TYPE { 
  WDI_PHY_TYPE_UNKNOWN     = 0,
  WDI_PHY_TYPE_ANY         = 0,
  WDI_PHY_TYPE_FHSS        = 1,
  WDI_PHY_TYPE_DSSS        = 2,
  WDI_PHY_TYPE_IRBASEBAND  = 3,
  WDI_PHY_TYPE_OFDM        = 4,
  WDI_PHY_TYPE_HRDSSS      = 5,
  WDI_PHY_TYPE_ERP         = 6,
  WDI_PHY_TYPE_HT          = 7,
  WDI_PHY_TYPE_VHT         = 8,
  WDI_PHY_TYPE_DMG         = 9,
  WDI_PHY_TYPE_IHV_START   = 0x80000000,
  WDI_PHY_TYPE_IHV_END     = 0xffffffff
} WDI_PHY_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_PHY_TYPE_ANY</td>
                    <td>Specifies an unknown or uninitialized PHY type.</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_DMG</td>
                    <td>Added in Windows 10, version 1607, WDI version 1.0.21.

Specifies an 802.11ad PHY.</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_DSSS</td>
                    <td>Specifies a direct sequence spread spectrum (DSSS) PHY.</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_ERP</td>
                    <td>Specifies an extended-rate 802.11g PHY (ERP).</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_FHSS</td>
                    <td>Specifies a frequency-hopping spread-spectrum (FHSS) PHY.</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_HRDSSS</td>
                    <td>Specifies a high-rate DSSS (HRDSSS) 802.11b PHY.</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_HT</td>
                    <td>Specifies a high-throughput (HT) 802.11n PHY. Each 802.11n PHY, whether dual-band or not, is specified as this PHY type.</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_IHV_END</td>
                    <td>Specifies the end of the range that is used to define proprietary PHY types that are developed by an IHV.</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_IHV_START</td>
                    <td>Specifies the start of the range that is used to define proprietary PHY types that are developed by an independent hardware vendor (IHV).</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_IRBASEBAND</td>
                    <td>Specifies an infrared (IR) baseband PHY.</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_OFDM</td>
                    <td>Specifies an orthogonal frequency division multiplexing (OFDM) 802.11a PHY.</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_UNKNOWN</td>
                    <td>Specifies an unknown or uninitialized PHY type.</td>
                </tr>
            
                <tr>
                    <td>WDI_PHY_TYPE_VHT</td>
                    <td>Specifies a very high-throughput (VHT) 802.11ac PHY.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |