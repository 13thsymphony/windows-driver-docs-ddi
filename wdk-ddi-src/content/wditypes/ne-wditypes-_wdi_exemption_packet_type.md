---
UID: NE:wditypes._WDI_EXEMPTION_PACKET_TYPE
title: "_WDI_EXEMPTION_PACKET_TYPE"
author: windows-driver-content
description: The WDI_EXEMPTION_PACKET_TYPE enumeration defines the types of packet exemptions.
old-location: netvista\wdi_exemption_packet_type.htm
old-project: netvista
ms.assetid: 7F584EBE-9ACB-4AC7-9472-34322F24EF74
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDI_EXEMPTION_PACKET_TYPE, WDI_EXEMPTION_PACKET_TYPE enumeration [Device and Driver Installation], WDI_EXEMPT_PACKET_TYPE_BOTH, WDI_EXEMPT_PACKET_TYPE_MULTICAST, WDI_EXEMPT_PACKET_TYPE_UNICAST, _WDI_EXEMPTION_PACKET_TYPE, netvista.wdi_exemption_packet_type, netvista.wifi_exemption_packet_type, wditypes/WDI_EXEMPTION_PACKET_TYPE, wditypes/WDI_EXEMPT_PACKET_TYPE_BOTH, wditypes/WDI_EXEMPT_PACKET_TYPE_MULTICAST, wditypes/WDI_EXEMPT_PACKET_TYPE_UNICAST
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
-	WDI_EXEMPTION_PACKET_TYPE
product: Windows
targetos: Windows
req.typenames: WDI_EXEMPTION_PACKET_TYPE
req.product: Windows 10 or later.
---

# _WDI_EXEMPTION_PACKET_TYPE Enumeration
The WDI_EXEMPTION_PACKET_TYPE enumeration defines the types of packet exemptions.

## Syntax
````
typedef enum _WDI_EXEMPTION_PACKET_TYPE { 
  WDI_EXEMPT_PACKET_TYPE_UNICAST    = 1,
  WDI_EXEMPT_PACKET_TYPE_MULTICAST  = 2,
  WDI_EXEMPT_PACKET_TYPE_BOTH       = 3
} WDI_EXEMPTION_PACKET_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_EXEMPT_PACKET_TYPE_BOTH</td>
                    <td>Exempt all packet types.</td>
                </tr>
            
                <tr>
                    <td>WDI_EXEMPT_PACKET_TYPE_MULTICAST</td>
                    <td>Exempt multicast and broadcast packets only.</td>
                </tr>
            
                <tr>
                    <td>WDI_EXEMPT_PACKET_TYPE_UNICAST</td>
                    <td>Exempt unicast packets only.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |