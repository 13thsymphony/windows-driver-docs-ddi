---
UID: NE.wwan._WWAN_PACKET_SERVICE_ACTION
title: _WWAN_PACKET_SERVICE_ACTION
author: windows-driver-content
description: The WWAN_PACKET_SERVICE_ACTION enumeration lists different packet service actions.
old-location: netvista\wwan_packet_service_action.htm
old-project: netvista
ms.assetid: 976e0d67-a03c-4545-b165-4b48062c03b7
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WWAN_PACKET_SERVICE_ACTION, WWAN_PACKET_SERVICE_ACTION, *PWWAN_PACKET_SERVICE_ACTION
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
req.alt-api: WWAN_PACKET_SERVICE_ACTION
req.alt-loc: wwan.h
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
req.product: Windows 10 or later.
---

# _WWAN_PACKET_SERVICE_ACTION enumeration



## -description
The WWAN_PACKET_SERVICE_ACTION enumeration lists different packet service actions.


## -syntax

````
typedef enum _WWAN_PACKET_SERVICE_ACTION { 
  WwanPacketServiceActionAttach  = 0,
  WwanPacketServiceActionDetach
} WWAN_PACKET_SERVICE_ACTION, *PWWAN_PACKET_SERVICE_ACTION;
````


## -enum-fields

### -field WwanPacketServiceActionAttach

Packet-attach to the registered provider.

### -field WwanPacketServiceActionDetach

Packet-detach from the registered provider.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows 7 and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_wwan_set_packet_service">NDIS_WWAN_SET_PACKET_SERVICE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PACKET_SERVICE_ACTION enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
