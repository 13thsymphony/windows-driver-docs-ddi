---
UID: NS.wsk._WSK_CLIENT_CONNECTION_DISPATCH
title: WSK_CLIENT_CONNECTION_DISPATCH
author: windows-driver-content
description: The WSK_CLIENT_CONNECTION_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a connection-oriented socket.
old-location: netvista\wsk_client_connection_dispatch.htm
old-project: netvista
ms.assetid: 960eee8a-2950-4baf-b32d-be13b3d65951
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WSK_CLIENT_CONNECTION_DISPATCH,
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
req.alt-api: WSK_CLIENT_CONNECTION_DISPATCH
req.alt-loc: wsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WSK_CLIENT_CONNECTION_DISPATCH structure



## -description
<p>The WSK_CLIENT_CONNECTION_DISPATCH structure specifies a WSK application's dispatch table of event
  callback functions for a connection-oriented socket.</p>


## -syntax

````
typedef struct _WSK_CLIENT_CONNECTION_DISPATCH {
  PFN_WSK_RECEIVE_EVENT      WskReceiveEvent;
  PFN_WSK_DISCONNECT_EVENT   WskDisconnectEvent;
  PFN_WSK_SEND_BACKLOG_EVENT WskSendBacklogEvent;
} WSK_CLIENT_CONNECTION_DISPATCH, *PWSK_CLIENT_CONNECTION_DISPATCH;
````


## -struct-fields
<dl>

### -field WskReceiveEvent

<dd>
<p>A pointer to the WSK application's 
     <a href="..\wsk\nc-wsk-pfn-wsk-receive-event.md">WskReceiveEvent</a> event callback function
     for the socket. If the WSK application does not enable the 
     <i>WskReceiveEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.</p>
</dd>

### -field WskDisconnectEvent

<dd>
<p>A pointer to the WSK application's 
     <a href="..\wsk\nc-wsk-pfn-wsk-disconnect-event.md">WskDisconnectEvent</a> event callback
     function for the socket. If the WSK application does not enable the 
     <i>WskDisconnectEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.</p>
</dd>

### -field WskSendBacklogEvent

<dd>
<p>A pointer to the WSK application's 
     <a href="..\wsk\nc-wsk-pfn-wsk-send-backlog-event.md">WskSendBacklogEvent</a> event callback
     function for the socket. If the WSK application does not enable the 
     <i>WskSendBacklogEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.</p>
</dd>
</dl>

## -remarks
<p>A WSK application passes a pointer to a WSK_CLIENT_CONNECTION_DISPATCH structure to the WSK subsystem
    in one of the following ways:</p>

<p>When calling the 
      <a href="..\wsk\nc-wsk-pfn-wsk-socket.md">WskSocket</a> function to create a
      connection-oriented socket.</p>

<p>When calling the 
      <a href="..\wsk\nc-wsk-pfn-wsk-socket-connect.md">WskSocketConnect</a> function to create,
      bind, and connect a connection-oriented socket.</p>

<p>When calling the 
      <a href="..\wsk\nc-wsk-pfn-wsk-accept.md">WskAccept</a> function to accept an incoming
      connection-oriented socket on a listening socket.</p>

<p>As a returned parameter when the WSK subsystem calls the WSK application's 
      <a href="..\wsk\nc-wsk-pfn-wsk-accept-event.md">WskAcceptEvent</a> event callback function.
      The WSK subsystem calls a WSK application's 
      <i>WskAcceptEvent</i> event callback function to notify the WSK application that an incoming
      connection-oriented socket has been accepted on a listening socket.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating
   systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-accept.md">WskAccept</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-socket.md">WskSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-socket-connect.md">WskSocketConnect</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-accept-event.md">WskAcceptEvent</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-disconnect-event.md">WskDisconnectEvent</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-receive-event.md">WskReceiveEvent</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn-wsk-send-backlog-event.md">WskSendBacklogEvent</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk--wsk-provider-connection-dispatch.md">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_CLIENT_CONNECTION_DISPATCH structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
