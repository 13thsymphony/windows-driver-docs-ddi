---
UID: NE:wditypes._WDI_CONNECTION_QUALITY_HINT
title: "_WDI_CONNECTION_QUALITY_HINT"
author: windows-driver-content
description: The WDI_CONNECTION_QUALITY_HINT enumeration defines the Wi-Fi connection quality hints.
old-location: netvista\wdi_connection_quality_hint.htm
old-project: netvista
ms.assetid: D83AE2BE-1273-48A1-A42C-C2EADA07D9C0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: WDI_CONNECTION_QUALITY_AUTO_POWER_SAVE, WDI_CONNECTION_QUALITY_HIGH_CHANNEL_AVAILABILITY, WDI_CONNECTION_QUALITY_HIGH_THROUGHPUT, WDI_CONNECTION_QUALITY_HINT, WDI_CONNECTION_QUALITY_HINT enumeration [Device and Driver Installation], WDI_CONNECTION_QUALITY_LOW_LATENCY, _WDI_CONNECTION_QUALITY_HINT, devinst.wfi_connection_quality_hint, netvista.wdi_connection_quality_hint, wditypes/WDI_CONNECTION_QUALITY_AUTO_POWER_SAVE, wditypes/WDI_CONNECTION_QUALITY_HIGH_CHANNEL_AVAILABILITY, wditypes/WDI_CONNECTION_QUALITY_HIGH_THROUGHPUT, wditypes/WDI_CONNECTION_QUALITY_HINT, wditypes/WDI_CONNECTION_QUALITY_LOW_LATENCY
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
-	WDI_CONNECTION_QUALITY_HINT
product: Windows
targetos: Windows
req.typenames: WDI_CONNECTION_QUALITY_HINT
req.product: Windows 10 or later.
---

# _WDI_CONNECTION_QUALITY_HINT Enumeration
The WDI_CONNECTION_QUALITY_HINT enumeration defines the Wi-Fi connection quality hints.

## Syntax
````
typedef enum _WDI_CONNECTION_QUALITY_HINT { 
  WDI_CONNECTION_QUALITY_AUTO_POWER_SAVE            = 1,
  WDI_CONNECTION_QUALITY_LOW_LATENCY                = 2,
  WDI_CONNECTION_QUALITY_HIGH_THROUGHPUT            = 3,
  WDI_CONNECTION_QUALITY_HIGH_CHANNEL_AVAILABILITY  = 4
} WDI_CONNECTION_QUALITY_HINT;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_CONNECTION_QUALITY_AUTO_POWER_SAVE</td>
                    <td>This hint indicates that the host has no specific preference for the usage of this port. The port should use power saving mechanisms when possible, as well as when other ports require a larger share of bandwidth/radio time. It can be enabled simultaneously on more than one port. This is the default Connection Quality setting for a port.</td>
                </tr>
            
                <tr>
                    <td>WDI_CONNECTION_QUALITY_LOW_LATENCY</td>
                    <td>This hint indicates that the host wants to use this port for low latency operations. The adapter should provide service to this port at a regular interval.
The WLAN schedule should be so that one way latency is no more than 30ms and packet loss &lt;=0.5% and no more than 3 consecutive packets are lost.
This can be set simultaneously on two ports. If the ports are on different channels, the max latency is relaxed to 50ms.  This is based on Windows Certification Programrequirements.
When in this mode, the port can (optionally) use power saving as long as it can meet the above latency requirements.</td>
                </tr>
            
                <tr>
                    <td>WDI_CONNECTION_QUALITY_HIGH_THROUGHPUT</td>
                    <td>Reserved.</td>
                </tr>
            
                <tr>
                    <td>WDI_CONNECTION_QUALITY_NO_POWER_SAVE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |