---
UID: NS:wsk._WSK_CLIENT_CONNECTION_DISPATCH
title: "_WSK_CLIENT_CONNECTION_DISPATCH"
author: windows-driver-content
description: The WSK_CLIENT_CONNECTION_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a connection-oriented socket.
old-location: netvista\wsk_client_connection_dispatch.htm
old-project: netvista
ms.assetid: 960eee8a-2950-4baf-b32d-be13b3d65951
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWSK_CLIENT_CONNECTION_DISPATCH, PWSK_CLIENT_CONNECTION_DISPATCH, PWSK_CLIENT_CONNECTION_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_CLIENT_CONNECTION_DISPATCH, WSK_CLIENT_CONNECTION_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_CLIENT_CONNECTION_DISPATCH, netvista.wsk_client_connection_dispatch, wsk/PWSK_CLIENT_CONNECTION_DISPATCH, wsk/WSK_CLIENT_CONNECTION_DISPATCH, wskref_2fd26ffb-dab8-4529-9fd0-6043509312c9.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
-	wsk.h
api_name:
-	WSK_CLIENT_CONNECTION_DISPATCH
product: Windows
targetos: Windows
req.typenames: WSK_CLIENT_CONNECTION_DISPATCH, *PWSK_CLIENT_CONNECTION_DISPATCH, WSK_CLIENT_CONNECTION_DISPATCH, *PWSK_CLIENT_CONNECTION_DISPATCH
req.product: Windows 10 or later.
---

# _WSK_CLIENT_CONNECTION_DISPATCH structure
The WSK_CLIENT_CONNECTION_DISPATCH structure specifies a WSK application's dispatch table of event
  callback functions for a connection-oriented socket.

## Syntax
````
typedef struct _WSK_CLIENT_CONNECTION_DISPATCH {
  PFN_WSK_RECEIVE_EVENT      WskReceiveEvent;
  PFN_WSK_DISCONNECT_EVENT   WskDisconnectEvent;
  PFN_WSK_SEND_BACKLOG_EVENT WskSendBacklogEvent;
} WSK_CLIENT_CONNECTION_DISPATCH, *PWSK_CLIENT_CONNECTION_DISPATCH;
````

## Members


`WskReceiveEvent`

A pointer to the WSK application's 
     <a href="..\wsk\nc-wsk-pfn_wsk_receive_event.md">WskReceiveEvent</a> event callback function
     for the socket. If the WSK application does not enable the 
     <i>WskReceiveEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.

`WskDisconnectEvent`

A pointer to the WSK application's 
     <a href="..\wsk\nc-wsk-pfn_wsk_disconnect_event.md">WskDisconnectEvent</a> event callback
     function for the socket. If the WSK application does not enable the 
     <i>WskDisconnectEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.

`WskSendBacklogEvent`

A pointer to the WSK application's 
     <a href="..\wsk\nc-wsk-pfn_wsk_send_backlog_event.md">WskSendBacklogEvent</a> event callback
     function for the socket. If the WSK application does not enable the 
     <i>WskSendBacklogEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.

## Remarks
A WSK application passes a pointer to a WSK_CLIENT_CONNECTION_DISPATCH structure to the WSK subsystem
    in one of the following ways:

<ul>
<li>
When calling the 
      <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create a
      connection-oriented socket.

</li>
<li>
When calling the 
      <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function to create,
      bind, and connect a connection-oriented socket.

</li>
<li>
When calling the 
      <a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a> function to accept an incoming
      connection-oriented socket on a listening socket.

</li>
<li>
As a returned parameter when the WSK subsystem calls the WSK application's 
      <a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a> event callback function.
      The WSK subsystem calls a WSK application's 
      <i>WskAcceptEvent</i> event callback function to notify the WSK application that an incoming
      connection-oriented socket has been accepted on a listening socket.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | wsk.h (include Wsk.h) |

## See Also

<a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>



<a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a>



<a href="..\wsk\nc-wsk-pfn_wsk_disconnect_event.md">WskDisconnectEvent</a>



<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>



<a href="..\wsk\nc-wsk-pfn_wsk_receive_event.md">WskReceiveEvent</a>



<a href="..\wsk\nc-wsk-pfn_wsk_send_backlog_event.md">WskSendBacklogEvent</a>



<a href="..\wsk\ns-wsk-_wsk_provider_connection_dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>