---
UID : NS:ntddndis._NDIS_LINK_STATE
title : _NDIS_LINK_STATE
author : windows-driver-content
description : The NDIS_LINK_STATE structure specifies the current link state of a miniport adapter.
old-location : netvista\ndis_link_state.htm
old-project : netvista
ms.assetid : 01d74e69-55fe-4e2e-94ab-7676f9e33403
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*PNDIS_LINK_STATE, PNDIS_LINK_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_LINK_STATE, NDIS_LINK_STATE structure [Network Drivers Starting with Windows Vista], NDIS_LINK_STATE, PNDIS_LINK_STATE, ntddndis/PNDIS_LINK_STATE, ntddndis/NDIS_LINK_STATE, netvista.ndis_link_state"
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_LINK_STATE, NDIS_LINK_STATE"
---

# _NDIS_LINK_STATE structure
The <b>NDIS_LINK_STATE</b> structure specifies the current link state of a miniport adapter.

## Syntax
````
typedef struct _NDIS_LINK_STATE {
  NDIS_OBJECT_HEADER             Header;
  NDIS_MEDIA_CONNECT_STATE       MediaConnectState;
  NDIS_MEDIA_DUPLEX_STATE        MediaDuplexState;
  ULONG64                        XmitLinkSpeed;
  ULONG64                        RcvLinkSpeed;
  NDIS_SUPPORTED_PAUSE_FUNCTIONS PauseFunctions;
  ULONG                          AutoNegotiationFlags;
} NDIS_LINK_STATE, *PNDIS_LINK_STATE;
````

## Members


`AutoNegotiationFlags`

The auto-negotiation settings for the miniport adapter. This member is created from a bitwise OR
 of the following flags:

`Header`

The 
      <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
 <b>NDIS_LINK_STATE</b> structure. Set the 
      <b>Type</b> member of the structure that 
      <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
      <b>Revision</b> member to NDIS_LINK_STATE_REVISION_1, and the 
      <b>Size</b> member to NDIS_SIZEOF_LINK_STATE_REVISION_1.

`MediaConnectState`

The media connect state for the miniport adapter. For more information, see  
      <mshelp:link keywords="netvista.oid_gen_media_connect_status_ex" tabindex="0">
 OID_GEN_MEDIA_CONNECT_STATUS_EX</mshelp:link> OID.

`MediaDuplexState`

The media duplex state for the miniport adapter. For more information, see <mshelp:link keywords="netvista.oid_gen_media_duplex_state" tabindex="0">
 OID_GEN_MEDIA_DUPLEX_STATE</mshelp:link> OID.

`PauseFunctions`

The type of support for the IEEE 802.3 pause frames. This member must be one of the following
 pause functions:

`RcvLinkSpeed`

The current receive link speed of the miniport adapter in bits per second. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>.

 
<div class="alert"><b>Note</b>  A value of NDIS_LINK_SPEED_UNKNOWN indicates that the
 receive link speed is unknown.</div><div> </div>

`XmitLinkSpeed`

The current transmit link speed of the miniport adapter in bits per second. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>.
 
<div class="alert"><b>Note</b>  A value of NDIS_LINK_SPEED_UNKNOWN indicates that the
 transmit link speed is unknown.</div><div> </div>

## Remarks
Miniport drivers use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567391">NDIS_STATUS_LINK_STATE</a> status indication to notify NDIS and overlying drivers that there has been a change in the physical characteristics of a medium.

When it generates this status indication, the driver sets the 
    <b>StatusBuffer</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a> structure to a pointer to an <b>NDIS_LINK_STATE</b> structure.

The miniport driver also returns an <b>NDIS_LINK_STATE</b> structure when it handles an OID query request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569595">OID_GEN_LINK_STATE</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff567391">NDIS_STATUS_LINK_STATE</a>

<mshelp:link keywords="netvista.oid_gen_media_connect_status_ex" tabindex="0">
 OID_GEN_MEDIA_CONNECT_STATUS_EX</mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569595">OID_GEN_LINK_STATE</a>

<a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a>

<mshelp:link keywords="netvista.oid_gen_media_duplex_state" tabindex="0">
 OID_GEN_MEDIA_DUPLEX_STATE</mshelp:link>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_LINK_STATE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>