---
UID : NE:wwan._WWAN_PACKET_SERVICE_ACTION
title : "_WWAN_PACKET_SERVICE_ACTION"
author : windows-driver-content
description : The WWAN_PACKET_SERVICE_ACTION enumeration lists different packet service actions.
old-location : netvista\wwan_packet_service_action.htm
old-project : netvista
ms.assetid : 976e0d67-a03c-4545-b165-4b48062c03b7
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wwan/PWWAN_PACKET_SERVICE_ACTION, PWWAN_PACKET_SERVICE_ACTION, _WWAN_PACKET_SERVICE_ACTION, wwan/WWAN_PACKET_SERVICE_ACTION, *PWWAN_PACKET_SERVICE_ACTION, WWAN_PACKET_SERVICE_ACTION, WwanPacketServiceActionAttach, WWAN_PACKET_SERVICE_ACTION enumeration [Network Drivers Starting with Windows Vista], wwan/WwanPacketServiceActionAttach, WwanPacketServiceActionDetach, wwan/WwanPacketServiceActionDetach, WwanRef_6ab5ff1d-9b6c-4018-8d3b-7753ebca12e4.xml, netvista.wwan_packet_service_action, PWWAN_PACKET_SERVICE_ACTION enumeration pointer [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wwan.h
req.include-header : Wwan.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WWAN_PACKET_SERVICE_ACTION, *PWWAN_PACKET_SERVICE_ACTION
req.product : Windows 10 or later.
---

# _WWAN_PACKET_SERVICE_ACTION Enumeration
The WWAN_PACKET_SERVICE_ACTION enumeration lists different packet service actions.

## Syntax
````
typedef enum _WWAN_PACKET_SERVICE_ACTION { 
  WwanPacketServiceActionAttach  = 0,
  WwanPacketServiceActionDetach
} WWAN_PACKET_SERVICE_ACTION, *PWWAN_PACKET_SERVICE_ACTION;
````

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

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_set_packet_service.md">NDIS_WWAN_SET_PACKET_SERVICE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PACKET_SERVICE_ACTION enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>