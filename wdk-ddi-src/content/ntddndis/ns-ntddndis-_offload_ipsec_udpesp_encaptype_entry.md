---
UID: NS:ntddndis._OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY
title: "_OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY"
author: windows-driver-content
description: The OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure specifies the UDP-ESP encapsulation type and destination port of a parser entry.
old-location: netvista\offload_ipsec_udpesp_encaptype_entry.htm
old-project: netvista
ms.assetid: a1e5ae2e-b183-4ccc-8413-1359c4e8a6bc
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure pointer [Network Drivers Starting with Windows Vista], OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure [Network Drivers Starting with Windows Vista], _OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, netvista.offload_ipsec_udpesp_encaptype_entry, *POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, ntddndis/POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, ntddndis/OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, 216offload_de874753-3127-47fb-8768-a5e2bd6eb96d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddndis.h
apiname:
-	OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY
product: Windows
targetos: Windows
req.typenames: "*POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY"
---

# _OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure
The OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure specifies the UDP-ESP encapsulation type and
  destination port of a parser entry.

## Syntax
````
typedef struct _OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY {
  UDP_ENCAP_TYPE UdpEncapType;
  USHORT         DstEncapPort;
} OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY, *POFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY;
````

## Members


`DstEncapPort`

For an inbound SA (Flags = OFFLOAD_INBOUND_SA), specifies the destination port that the NIC should
     look for in the UDP header of inbound packets that it processes on the SAs being offloaded. The NIC
     should ignore this member for an outbound SA (
     <b>Flags</b> = 
     <b>OFFLOAD_OUTBOUND_SA</b>). 
     <b>DstEncapPort</b> should always specify port 4500.

`UdpEncapType`

The UDP-ESP encapsulation type for packets protected by the security associations (SAs) that are
     being offloaded:
     





#### IPSEC_UDPESP_ENCAPTYPE_IKE

This value is reserved.



#### IPSEC_UDPESP_E\NCAPTYPE_OTHER

UDP encapsulation for packets on port 4500. For more information, see 
       <a href="https://msdn.microsoft.com/86556307-d877-4ee6-bf7f-82160a0b9078">UDP-ESP Encapsulation
       Types</a>.

## Remarks
The OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure is used with the 
    <a href="..\ntddndis\ns-ntddndis-_offload_ipsec_add_udpesp_sa.md">
    OFFLOAD_IPSEC_ADD_UDPESP_SA</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_offload_ipsec_add_udpesp_sa.md">OFFLOAD_IPSEC_ADD_UDPESP_SA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20OFFLOAD_IPSEC_UDPESP_ENCAPTYPE_ENTRY structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>