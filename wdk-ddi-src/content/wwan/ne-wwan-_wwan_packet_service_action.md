---
UID: NE:wwan._WWAN_PACKET_SERVICE_ACTION
title: "_WWAN_PACKET_SERVICE_ACTION"
author: windows-driver-content
description: The WWAN_PACKET_SERVICE_ACTION enumeration lists different packet service actions.
old-location: netvista\wwan_packet_service_action.htm
old-project: netvista
ms.assetid: 976e0d67-a03c-4545-b165-4b48062c03b7
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_PACKET_SERVICE_ACTION, PWWAN_PACKET_SERVICE_ACTION, PWWAN_PACKET_SERVICE_ACTION enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_PACKET_SERVICE_ACTION, WWAN_PACKET_SERVICE_ACTION enumeration [Network Drivers Starting with Windows Vista], WwanPacketServiceActionAttach, WwanPacketServiceActionDetach, WwanRef_6ab5ff1d-9b6c-4018-8d3b-7753ebca12e4.xml, _WWAN_PACKET_SERVICE_ACTION, netvista.wwan_packet_service_action, wwan/PWWAN_PACKET_SERVICE_ACTION, wwan/WWAN_PACKET_SERVICE_ACTION, wwan/WwanPacketServiceActionAttach, wwan/WwanPacketServiceActionDetach"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_PACKET_SERVICE_ACTION
product:
- Windows
targetos: Windows
req.typenames: WWAN_PACKET_SERVICE_ACTION, *PWWAN_PACKET_SERVICE_ACTION
req.product: Windows 10 or later.
---

# _WWAN_PACKET_SERVICE_ACTION Enumeration
The WWAN_PACKET_SERVICE_ACTION enumeration lists different packet service actions.

## Syntax
```
typedef enum _WWAN_PACKET_SERVICE_ACTION {
  WwanPacketServiceActionAttach  ,
  WwanPacketServiceActionDetach
} WWAN_PACKET_SERVICE_ACTION, *PWWAN_PACKET_SERVICE_ACTION;
```

## Constants

<table>
            
                <tr>
                    <td>WwanPacketServiceActionAttach</td>
                    <td>Packet-attach to the registered provider.</td>
                </tr>
            
                <tr>
                    <td>WwanPacketServiceActionDetach</td>
                    <td>Packet-detach from the registered provider.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567921">NDIS_WWAN_SET_PACKET_SERVICE</a>