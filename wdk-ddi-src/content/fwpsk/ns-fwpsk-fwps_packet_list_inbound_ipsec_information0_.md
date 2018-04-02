---
UID: NS:fwpsk.FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0_
title: FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0_
author: windows-driver-content
description: The FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0 structure defines IPsec information associated with inbound packet data.Note  FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0 is a specific version of FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION.
old-location: netvista\fwps_packet_list_inbound_ipsec_information0.htm
old-project: netvista
ms.assetid: ac5994a7-411c-47f2-ba1d-2d49c727de8d
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0, FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0 structure [Network Drivers Starting with Windows Vista], FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0_, fwpsk/FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0, netvista.fwps_packet_list_inbound_ipsec_information0, wfp_ref_3_struct_3_fwps_P-Z_3acc4a2d-78ef-418a-ab15-a9e306110baf.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0
product:
- Windows
targetos: Windows
req.typenames: FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0
---

# FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0_ structure
The <b>FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0</b> structure defines IPsec information associated with
  inbound packet data.
<div class="alert"><b>Note</b>  <b>FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0</b> is a specific version of <b>FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## Syntax
```
typedef struct FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0_ {
  unsigned  : 1 isSecure;
  unsigned  : 1 isTransportMode;
  unsigned  : 1 isTunnelMode;
  unsigned  : 1 isTransportModeVerified;
  unsigned  : 1 isTunnelModeVerified;
  unsigned  : 1 isDeTunneled;
} FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0;
```

## Members


`isSecure`

A value that indicates whether IPsec tunnel mode or IPsec transport mode processing has been performed
     on the packet list.

`isTransportMode`

A value that indicates whether IPsec has applied a transport mode security association to the packet
     list.

`isTunnelMode`

A value that indicates whether IPsec has applied a tunnel mode security association to the packet
     list.

`isTransportModeVerified`

A value that indicates whether the packet list has been verified against the IPsec transport mode
     filter in the inbound transport layer.

`isTunnelModeVerified`

A value that indicates whether the packet list has been verified against the IPsec tunnel mode filter
     in the inbound transport layer.

`isDeTunneled`

A value that indicates whether the packet list has been detunneled by IPsec.

## Remarks
An FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0 structure is included as a member of the 
    <a href="https://msdn.microsoft.com/bd005dd9-887a-4323-9816-e4a3b96ca53d">
    FWPS_PACKET_LIST_IPSEC_INFORMATION0</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows Vista. Available starting with Windows Vista. |
| **Header** | fwpsk.h (include Fwpsk.h) |

## See Also

<a href="https://msdn.microsoft.com/bd005dd9-887a-4323-9816-e4a3b96ca53d">
   FWPS_PACKET_LIST_IPSEC_INFORMATION0</a>