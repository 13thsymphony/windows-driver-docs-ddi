---
UID: NE:wditypes._WDI_P2P_SERVICE_DISCOVERY_TYPE
title: "_WDI_P2P_SERVICE_DISCOVERY_TYPE"
author: windows-driver-content
description: The WDI_P2P_SERVICE_DISCOVERY_TYPE enumeration defines the types of service discovery.
old-location: netvista\wdi_p2p_service_discovery_type.htm
old-project: netvista
ms.assetid: 5CA8F330-7AFE-44C9-BCCA-CA93479B9754
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDI_P2P_SERVICE_DISCOVERY_TYPE, WDI_P2P_SERVICE_DISCOVERY_TYPE enumeration [Network Drivers Starting with Windows Vista], WDI_P2P_SERVICE_DISCOVERY_TYPE_ASP2_SERVICE_INFORMATION, WDI_P2P_SERVICE_DISCOVERY_TYPE_ASP2_SERVICE_NAME_ONLY, WDI_P2P_SERVICE_DISCOVERY_TYPE_NO_SERVICE_DISCOVERY, WDI_P2P_SERVICE_DISCOVERY_TYPE_SERVICE_INFORMATION, WDI_P2P_SERVICE_DISCOVERY_TYPE_SERVICE_NAME_ONLY, _WDI_P2P_SERVICE_DISCOVERY_TYPE, netvista.wdi_p2p_service_discovery_type, wditypes/WDI_P2P_SERVICE_DISCOVERY_TYPE, wditypes/WDI_P2P_SERVICE_DISCOVERY_TYPE_ASP2_SERVICE_INFORMATION, wditypes/WDI_P2P_SERVICE_DISCOVERY_TYPE_ASP2_SERVICE_NAME_ONLY, wditypes/WDI_P2P_SERVICE_DISCOVERY_TYPE_NO_SERVICE_DISCOVERY, wditypes/WDI_P2P_SERVICE_DISCOVERY_TYPE_SERVICE_INFORMATION, wditypes/WDI_P2P_SERVICE_DISCOVERY_TYPE_SERVICE_NAME_ONLY
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
-	WDI_P2P_SERVICE_DISCOVERY_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_P2P_SERVICE_DISCOVERY_TYPE
req.product: Windows 10 or later.
---

# _WDI_P2P_SERVICE_DISCOVERY_TYPE Enumeration
The WDI_P2P_SERVICE_DISCOVERY_TYPE enumeration defines the types of service discovery.

## Syntax
````
typedef enum _WDI_P2P_SERVICE_DISCOVERY_TYPE { 
  WDI_P2P_SERVICE_DISCOVERY_TYPE_NO_SERVICE_DISCOVERY      = 1,
  WDI_P2P_SERVICE_DISCOVERY_TYPE_SERVICE_NAME_ONLY         = 2,
  WDI_P2P_SERVICE_DISCOVERY_TYPE_SERVICE_INFORMATION       = 3,
  WDI_P2P_SERVICE_DISCOVERY_TYPE_ASP2_SERVICE_NAME_ONLY    = 4,
  WDI_P2P_SERVICE_DISCOVERY_TYPE_ASP2_SERVICE_INFORMATION  = 5
} WDI_P2P_SERVICE_DISCOVERY_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_P2P_SERVICE_DISCOVERY_TYPE_MAX_VALUE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WDI_P2P_SERVICE_DISCOVERY_TYPE_NO_SERVICE_DISCOVERY</td>
                    <td>The adapter should only do a WFD discovery for WFD devices.  It should not encode service hashes in the P2P IEs.</td>
                </tr>
            
                <tr>
                    <td>WDI_P2P_SERVICE_DISCOVERY_TYPE_SERVICE_INFORMATION</td>
                    <td>The adapter encodes the service hashes in the IEs, tracks the service names from the probe responses, and does GAS queries to get service information for each responding device.  This is only applicable if the adapter supports the P2P Service Information Discovery capability.</td>
                </tr>
            
                <tr>
                    <td>WDI_P2P_SERVICE_DISCOVERY_TYPE_SERVICE_NAME_ONLY</td>
                    <td>The adapter encodes service hashes in the P2P IEs during probe requests and indicates probe responses.  It does not perform any GAS queries for service information.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |