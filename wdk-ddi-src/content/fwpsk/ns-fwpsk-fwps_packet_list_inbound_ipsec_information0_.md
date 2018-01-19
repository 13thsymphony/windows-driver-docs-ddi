---
UID : NS:fwpsk.FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0_
title : FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0_
author : windows-driver-content
description : The FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0 structure defines IPsec information associated with inbound packet data.Note  FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0 is a specific version of FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION.
old-location : netvista\fwps_packet_list_inbound_ipsec_information0.htm
old-project : netvista
ms.assetid : ac5994a7-411c-47f2-ba1d-2d49c727de8d
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0_, FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : fwpsk.h
req.include-header : Fwpsk.h
req.target-type : Windows
req.target-min-winverclnt : Available starting with Windows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0
req.alt-loc : fwpsk.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0
---

# FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0_ structure
The <b>FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0</b> structure defines IPsec information associated with
  inbound packet data.

## Syntax
````
typedef struct FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0_ {
  unsigned isSecure  :1;
  unsigned isTransportMode  :1;
  unsigned isTunnelMode  :1;
  unsigned isTransportModeVerified  :1;
  unsigned isTunnelModeVerified  :1;
  unsigned isDeTunneled  :1;
} FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0;
````

## Members

        
            `isDeTunneled`

            A value that indicates whether the packet list has been detunneled by IPsec.
        
            `isSecure`

            A value that indicates whether IPsec tunnel mode or IPsec transport mode processing has been performed
     on the packet list.
        
            `isTransportMode`

            A value that indicates whether IPsec has applied a transport mode security association to the packet
     list.
        
            `isTransportModeVerified`

            A value that indicates whether the packet list has been verified against the IPsec transport mode
     filter in the inbound transport layer.
        
            `isTunnelMode`

            A value that indicates whether IPsec has applied a tunnel mode security association to the packet
     list.
        
            `isTunnelModeVerified`

            A value that indicates whether the packet list has been verified against the IPsec tunnel mode filter
     in the inbound transport layer.

    ## Remarks
        An FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0 structure is included as a member of the 
    <a href="..\fwpsk\ns-fwpsk-fwps_packet_list_ipsec_information0_.md">
    FWPS_PACKET_LIST_IPSEC_INFORMATION0</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fwpsk.h (include Fwpsk.h) |

    ## See Also

        <dl>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_packet_list_ipsec_information0_.md">
   FWPS_PACKET_LIST_IPSEC_INFORMATION0</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_PACKET_LIST_INBOUND_IPSEC_INFORMATION0 structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>