---
UID: NC.wsk.PFN_WSK_DISCONNECT_EVENT
title: PFN_WSK_DISCONNECT_EVENT
author: windows-driver-content
description: The WskDisconnectEvent event callback function notifies a WSK application that a connection on a connection-oriented socket has been disconnected by the remote application.
old-location: netvista\wskdisconnectevent.htm
old-project: NetVista
ms.assetid: bf12d7b3-080e-46d9-b276-76d42068e7c6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO, PWPP_TRIAGE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WskDisconnectEvent
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
req.product: Windows 10 or later.
---

# PFN_WSK_DISCONNECT_EVENT callback



## -description
The 
  <i>WskDisconnectEvent</i> event callback function notifies a WSK application that a connection on a
  connection-oriented socket has been disconnected by the remote application.



## -prototype

````
PFN_WSK_DISCONNECT_EVENT WskDisconnectEvent;

NTSTATUS APIENTRY WskDisconnectEvent(
  _In_opt_ PVOID SocketContext,
  _In_     ULONG Flags
)
{ ... }
````


## -parameters

### -param SocketContext [in, optional]

A pointer to the socket context for the connection-oriented socket that has been disconnected. The
     WSK application provided this pointer to the WSK subsystem in one of the following ways:
     

<ul>
<li>
It called the 
       <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create the socket.

</li>
<li>
It called the 
       <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function to create
       the socket.

</li>
<li>
It called the 
       <a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a> function to accept the socket as an
       incoming connection.

</li>
<li>
Its 
       <a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a> event callback function
       was called to accept the socket as an incoming connection.

</li>
</ul>

### -param Flags [in]

A ULONG value that contains a bitwise OR of a combination of the following flags:
     




### -param WSK_FLAG_ABORTIVE

The remote application performed an abortive disconnect of the socket. If this flag is not set,
       the remote application performed a graceful disconnect of the socket.


### -param WSK_FLAG_AT_DISPATCH_LEVEL

The WSK subsystem called the 
       <i>WskDisconnectEvent</i> event callback function at IRQL = DISPATCH_LEVEL. If this flag is not set,
       the WSK subsystem might have called the 
       <i>WskDisconnectEvent</i> event callback function at any IRQL &lt;= DISPATCH_LEVEL.

</dd>
</dl>

## -returns
A WSK application's 
     <i>WskDisconnectEvent</i> event callback function must always return STATUS_SUCCESS.


## -remarks
The WSK subsystem calls a WSK application's 
    <i>WskDisconnectEvent</i> event callback function when a connection-oriented socket is disconnected by the
    remote application only if the event callback function was previously enabled with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a> socket option.
    For more information about enabling a socket's event callback functions, see 
    <a href="netvista.enabling_and_disabling_event_callback_functions">Enabling and
    Disabling Event Callback Functions</a>.

If the remote application performed a graceful disconnect of the socket, no further data will be
    received from the socket. However, the WSK application can still send data to the socket until the socket
    is either completely closed by the remote application or the WSK application calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_disconnect.md">WskDisconnect</a> function or the 
    <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function on the socket.

If the remote application performed an abortive disconnect of the socket, no further data will be
    received from the socket and no further data can be sent to the socket.

The WSK subsystem calls a WSK application's 
    <i>WskDisconnectEvent</i> event callback function at IRQL &lt;= DISPATCH_LEVEL.

A WSK application's <i>WskDisconnectEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_connect.md">WskConnect</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_disconnect.md">WskDisconnect</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a>
</dt>
<dt>
<a href="netvista.wsk_client_connection_dispatch">
   WSK_CLIENT_CONNECTION_DISPATCH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20PFN_WSK_DISCONNECT_EVENT callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

