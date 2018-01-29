---
UID : NS:ndischimney._NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
title : _NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
author : windows-driver-content
description : The NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies a protocol or intermediate driver's TCP chimney offload-specific entry points.
old-location : netvista\ndis_client_chimney_offload_tcp_characteristics.htm
old-project : netvista
ms.assetid : 1925cfd4-f83f-48a5-b928-2c663ac0dc61
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.ndis_client_chimney_offload_tcp_characteristics, ndischimney/PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, tcp_chim_struct_8bfa1be6-3a5f-463a-a2c2-8f2a1f7e55e3.xml, ndischimney/NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, *PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, _NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndischimney.h
req.include-header : Ndischimney.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.typenames : "*PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS"
---

# _NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies a protocol or intermediate
  driver's TCP chimney offload-specific entry points.

## Syntax
````
typedef struct _NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                      Header;
  ULONG                                   Flags;
  NDIS_CHIMNEY_OFFLOAD_TYPE               OffloadType;
  TCP_OFFLOAD_SEND_COMPLETE_HANDLER       TcpOffloadSendCompleteHandler;
  TCP_OFFLOAD_RECV_COMPLETE_HANDLER       TcpOffloadReceiveCompleteHandler;
  TCP_OFFLOAD_DISCONNECT_COMPLETE_HANDLER TcpOffloadDisconnectCompleteHandler;
  TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER    TcpOffloadForwardCompleteHandler;
  TCP_OFFLOAD_EVENT_HANDLER               TcpOffloadEventHandler;
  TCP_OFFLOAD_RECEIVE_INDICATE_HANDLER    TcpOffloadReceiveIndicateHandler;
} NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, *PNDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS;
````

## Members


`Flags`

Reserved for system use.

`Header`

The header of the NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure and the size of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.

`OffloadType`

The chimney offload type. The only allowable value is 
     <b>NdisTcpChimneyOffload</b>, which specifies a TCP chimney.

`TcpOffloadDisconnectCompleteHandler`

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocoltcpoffloaddisconnectcomplete" tabindex="0"><i>
     ProtocolTcpOffloadDisconnectComplete</i></mshelp:link> function.

`TcpOffloadEventHandler`

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocoltcpoffloadevent" tabindex="0"><i>
     ProtocolTcpOffloadEvent</i></mshelp:link> function.

`TcpOffloadForwardCompleteHandler`

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocoltcpoffloadforwardcomplete" tabindex="0"><i>
     ProtocolTcpOffloadForwardComplete</i></mshelp:link> function.

`TcpOffloadReceiveCompleteHandler`

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocoltcpoffloadreceivecomplete" tabindex="0"><i>
     ProtocolTcpOffloadReceiveComplete</i></mshelp:link> function.

`TcpOffloadReceiveIndicateHandler`

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocoltcpoffloadreceiveindicate" tabindex="0"><i>
     ProtocolTcpOffloadReceiveIndicate</i></mshelp:link> function.

`TcpOffloadSendCompleteHandler`

The entry point of the driver's 
     <mshelp:link keywords="netvista.protocoltcpoffloadsendcomplete" tabindex="0"><i>
     ProtocolTcpOffloadSendComplete</i></mshelp:link> function.

## Remarks
To register its TCP chimney offload entry points, a protocol or intermediate driver calls the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function, the protocol or intermediate driver passes a pointer to the
    NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndischimney.h (include Ndischimney.h) |

## See Also

<mshelp:link keywords="netvista.protocoltcpoffloadreceivecomplete" tabindex="0"><i>
   ProtocolTcpOffloadReceiveComplete</i></mshelp:link>

<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>

<mshelp:link keywords="netvista.protocoltcpoffloadsendcomplete" tabindex="0"><i>
   ProtocolTcpOffloadSendComplete</i></mshelp:link>

<a href="..\ndischimney\nc-ndischimney-tcp_offload_event_handler.md">ProtocolTcpOffloadEvent</a>

<a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a>

<mshelp:link keywords="netvista.protocoltcpoffloaddisconnectcomplete" tabindex="0"><i>
   ProtocolTcpOffloadDisconnectComplete</i></mshelp:link>

<mshelp:link keywords="netvista.protocoltcpoffloadreceiveindicate" tabindex="0"><i>
   ProtocolTcpOffloadReceiveIndicate</i></mshelp:link>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_CLIENT_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>