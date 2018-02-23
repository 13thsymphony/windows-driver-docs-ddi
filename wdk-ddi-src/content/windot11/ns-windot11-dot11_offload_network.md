---
UID: NS:windot11.DOT11_OFFLOAD_NETWORK
title: DOT11_OFFLOAD_NETWORK
author: windows-driver-content
description: The DOT11_OFFLOAD_NETWORK structure describes a network list offload.
old-location: netvista\dot11_offload_network.htm
old-project: netvista
ms.assetid: 75DC558F-801B-42ED-9282-127E86E78923
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.dot11_offload_network, DOT11_OFFLOAD_NETWORK, PDOT11_OFFLOAD_NETWORK structure pointer [Network Drivers Starting with Windows Vista], *PDOT11_OFFLOAD_NETWORK, windot11/DOT11_OFFLOAD_NETWORK, PDOT11_OFFLOAD_NETWORK, windot11/PDOT11_OFFLOAD_NETWORK, DOT11_OFFLOAD_NETWORK structure [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
req.target-min-winversvr: 
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
-	Windot11.h
apiname:
-	DOT11_OFFLOAD_NETWORK
product: Windows
targetos: Windows
req.typenames: DOT11_OFFLOAD_NETWORK, *PDOT11_OFFLOAD_NETWORK
req.product: Windows 10 or later.
---

# DOT11_OFFLOAD_NETWORK structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_OFFLOAD_NETWORK structure describes a network list offload.

## Syntax
````
typedef struct _DOT11_OFFLOAD_NETWORK {
  DOT11_SSID             Ssid;
  DOT11_CIPHER_ALGORITHM UnicastCipher;
  DOT11_AUTH_ALGORITHM   AuthAlgo;
  DOT11_CHANNEL_HINT     Dot11ChannelHints[DOT11_MAX_CHANNEL_HINTS];
} DOT11_OFFLOAD_NETWORK, *PDOT11_OFFLOAD_NETWORK;
````

## Members


`AuthAlgo`

Wireless LAN authentication algorithm.

`Dot11ChannelHints`



`Ssid`

SSID interface.

`UnicastCipher`

Cipher algorithm for data encryption and decryption.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows 8 Versions:\_Supported in Windows 8 |
| **Header** | windot11.h (include Windot11.h) |