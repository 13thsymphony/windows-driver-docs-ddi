---
UID: NS.NDISCHIMNEY._NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
title: _NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
author: windows-driver-content
description: The NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies an offload target's TCP chimney offload-specific entry points.
old-location: netvista\ndis_provider_chimney_offload_tcp_characteristics.htm
old-project: netvista
ms.assetid: 3eabbad5-b84b-4034-a0b6-d4d515cbc117
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS
req.alt-loc: ndischimney.h
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
---

# _NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure specifies an offload target's TCP
  chimney offload-specific entry points.



## -syntax

````
typedef struct _NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                   Header;
  ULONG                                Flags;
  NDIS_CHIMNEY_OFFLOAD_TYPE            OffloadType;
  W_TCP_OFFLOAD_SEND_HANDLER           TcpOffloadSendHandler;
  W_TCP_OFFLOAD_RECEIVE_HANDLER        TcpOffloadReceiveHandler;
  W_TCP_OFFLOAD_DISCONNECT_HANDLER     TcpOffloadDisconnectHandler;
  W_TCP_OFFLOAD_FORWARD_HANDLER        TcpOffloadForwardHandler;
  W_TCP_OFFLOAD_RECEIVE_RETURN_HANDLER TcpOffloadReceiveReturnHandler;
} NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS;
````


## -struct-fields

### -field Header

The header of the NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure and the size of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.


### -field Flags

Reserved for system use.


### -field OffloadType

The chimney offload type. The only allowable value is 
     <b>NdisTcpChimneyOffload</b>, which specifies a TCP chimney.


### -field TcpOffloadSendHandler

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">
     MiniportTcpOffloadSend</a> function.


### -field TcpOffloadReceiveHandler

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">
     MiniportTcpOffloadReceive</a> function.


### -field TcpOffloadDisconnectHandler

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
     MiniportTcpOffloadDisconnect</a> function.


### -field TcpOffloadForwardHandler

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">
     MiniportTcpOffloadForward</a> function.


### -field TcpOffloadReceiveReturnHandler

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_return_handler.md">
     MiniportTcpOffloadReceiveReturn</a> function.


## -remarks
To register its TCP chimney offload-specific entry points, an offload target calls the 
    <a href="netvista.ndissetoptionalhandlers">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="netvista.miniportsetoptions">MiniportSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function, the offload target passes a pointer to the
    NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.miniportsetoptions">MiniportSetOptions</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_disconnect_handler.md">
   MiniportTcpOffloadDisconnect</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">MiniportTcpOffloadForward</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">MiniportTcpOffloadReceive</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_return_handler.md">
   MiniportTcpOffloadReceiveReturn</a>
</dt>
<dt>
<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_send_handler.md">MiniportTcpOffloadSend</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndissetoptionalhandlers">NdisSetOptionalHandlers</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROVIDER_CHIMNEY_OFFLOAD_TCP_CHARACTERISTICS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

