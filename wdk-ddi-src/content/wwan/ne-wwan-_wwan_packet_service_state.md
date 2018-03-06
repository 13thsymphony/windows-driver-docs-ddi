---
UID: NE:wwan._WWAN_PACKET_SERVICE_STATE
title: "_WWAN_PACKET_SERVICE_STATE"
author: windows-driver-content
description: The WWAN_PACKET_SERVICE_STATE enumeration lists the different packet service attachment states that are supported by the MB device.
old-location: netvista\wwan_packet_service_state.htm
old-project: netvista
ms.assetid: 542a8a3b-7704-434c-ad81-0cf8e1f70015
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWWAN_PACKET_SERVICE_STATE, PWWAN_PACKET_SERVICE_STATE, PWWAN_PACKET_SERVICE_STATE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_PACKET_SERVICE_STATE, WWAN_PACKET_SERVICE_STATE enumeration [Network Drivers Starting with Windows Vista], WwanPacketServiceStateAttached, WwanPacketServiceStateAttaching, WwanPacketServiceStateDetached, WwanPacketServiceStateDetaching, WwanPacketServiceStateUnknown, WwanRef_c342b0ee-c3da-4199-9172-4e2fb538f64b.xml, _WWAN_PACKET_SERVICE_STATE, netvista.wwan_packet_service_state, wwan/PWWAN_PACKET_SERVICE_STATE, wwan/WWAN_PACKET_SERVICE_STATE, wwan/WwanPacketServiceStateAttached, wwan/WwanPacketServiceStateAttaching, wwan/WwanPacketServiceStateDetached, wwan/WwanPacketServiceStateDetaching, wwan/WwanPacketServiceStateUnknown"
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
-	WWAN_PACKET_SERVICE_STATE
product: Windows
targetos: Windows
req.typenames: WWAN_PACKET_SERVICE_STATE, *PWWAN_PACKET_SERVICE_STATE
req.product: Windows 10 or later.
---

# _WWAN_PACKET_SERVICE_STATE Enumeration
The WWAN_PACKET_SERVICE_STATE enumeration lists the different packet service attachment states that
  are supported by the MB device.

## Syntax
````
typedef enum _WWAN_PACKET_SERVICE_STATE { 
  WwanPacketServiceStateUnknown    = 0,
  WwanPacketServiceStateAttaching,
  WwanPacketServiceStateAttached,
  WwanPacketServiceStateDetaching,
  WwanPacketServiceStateDetached
} WWAN_PACKET_SERVICE_STATE, *PWWAN_PACKET_SERVICE_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>WwanPacketServiceStateAttached</td>
                    <td>Packet service is attached.</td>
                </tr>
            
                <tr>
                    <td>WwanPacketServiceStateAttaching</td>
                    <td>Packet service attach action is in progress.</td>
                </tr>
            
                <tr>
                    <td>WwanPacketServiceStateDetached</td>
                    <td>Packet service is detached.</td>
                </tr>
            
                <tr>
                    <td>WwanPacketServiceStateDetaching</td>
                    <td>Packet service detach action is in progress.</td>
                </tr>
            
                <tr>
                    <td>WwanPacketServiceStateUnknown</td>
                    <td>Packet service state is unknown. The miniport driver should specify this state on a failure to set
     the MB packet service state.</td>
                </tr>
</table>

## Remarks

The packet service attach or detach state is typically reflected in the device's user interface.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_packet_service.md">WWAN_PACKET_SERVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PACKET_SERVICE_STATE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>