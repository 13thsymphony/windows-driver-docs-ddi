---
UID: NE:dot11wdi._WDI_TXRX_PEER_QOS_CAPS
title: "_WDI_TXRX_PEER_QOS_CAPS"
author: windows-driver-content
description: The WDI_TXRX_PEER_QOS_CAPS enumeration defines the Quality of Service (QoS) capabilities.
old-location: netvista\wdi_txrx_peer_qos_caps.htm
old-project: netvista
ms.assetid: 34d53daa-3501-4532-82e3-e5b0ed452b66
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WDI_TXRX_PEER_QOS_CAPS enumeration [Network Drivers Starting with Windows Vista], WDI_TXRX_PEER_QOS_CAPS, dot11wdi/WDI_TXRX_PeerCfgQosUapsdTids, dot11wdi/WDI_TXRX_PeerCfgQosCapable, WDI_TXRX_PeerCfgQosCapable, WDI_TXRX_PeerCfgQosNone, netvista.wifi_txrx_peer_qos_caps, netvista.wdi_txrx_peer_qos_caps, _WDI_TXRX_PEER_QOS_CAPS, dot11wdi/WDI_TXRX_PeerCfgQosNone, WDI_TXRX_PeerCfgQosUapsdTids, dot11wdi/WDI_TXRX_PEER_QOS_CAPS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dot11wdi.h
apiname:
-	WDI_TXRX_PEER_QOS_CAPS
product: Windows
targetos: Windows
req.typenames: WDI_TXRX_PEER_QOS_CAPS
---

# _WDI_TXRX_PEER_QOS_CAPS Enumeration
The WDI_TXRX_PEER_QOS_CAPS enumeration defines the Quality of Service (QoS) capabilities.

## Syntax
````
typedef enum _WDI_TXRX_PEER_QOS_CAPS { 
  WDI_TXRX_PeerCfgQosNone       = 0,
  WDI_TXRX_PeerCfgQosCapable    = 1,
  WDI_TXRX_PeerCfgQosUapsdTids  = 2
} WDI_TXRX_PEER_QOS_CAPS;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_TXRX_PeerCfgQosCapable</td>
                    <td>Specifies that QoS was negotiated for this peer during association.</td>
                </tr>
            
                <tr>
                    <td>WDI_TXRX_PeerCfgQosNone</td>
                    <td>Specifies that QoS was not negotiated for this peer during association.</td>
                </tr>
            
                <tr>
                    <td>WDI_TXRX_PeerCfgUapsdTids</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |