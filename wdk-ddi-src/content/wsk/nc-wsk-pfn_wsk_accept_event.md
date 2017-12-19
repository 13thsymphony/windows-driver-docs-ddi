---
UID: NC.wsk.PFN_WSK_ACCEPT_EVENT
title: PFN_WSK_ACCEPT_EVENT
author: windows-driver-content
description: The WskAcceptEvent event callback function notifies a WSK application that an incoming connection on a listening socket has been accepted.
old-location: netvista\wskacceptevent.htm
old-project: NetVista
ms.assetid: 672440f0-810a-4e68-82a5-d038770898c5
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
req.alt-api: WskAcceptEvent
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

# PFN_WSK_ACCEPT_EVENT callback



## -description
The 
  <i>WskAcceptEvent</i> event callback function notifies a WSK application that an incoming connection on a
  listening socket has been accepted.



## -prototype

````
PFN_WSK_ACCEPT_EVENT WskAcceptEvent;

NTSTATUS APIENTRY WskAcceptEvent(
  _In_opt_       PVOID                          SocketContext,
  _In_           ULONG                          Flags,
  _In_           PSOCKADDR                      LocalAddress,
  _In_           PSOCKADDR                      RemoteAddress,
  _In_opt_       PWSK_SOCKET                    AcceptSocket,
  _Out_          PVOID                          *AcceptSocketContext,
  _Out_    const WSK_CLIENT_CONNECTION_DISPATCH **AcceptSocketDispatch
)
{ ... }
````


## -parameters

### -param SocketContext [in, optional]

A pointer to the socket context for the listening socket on which the incoming connection was
     accepted. The WSK application provided this pointer to the WSK subsystem when it called the 
     <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create the listening
     socket.


### -param Flags [in]

A ULONG value that contains the following flag, or zero:
     




### -param WSK_FLAG_AT_DISPATCH_LEVEL

The WSK subsystem called the 
       <i>WskAcceptEvent</i> event callback function at IRQL = DISPATCH_LEVEL. If this flag is not set, the
       WSK subsystem might have called the 
       <i>WskAcceptEvent</i> event callback function at any IRQL &lt;= DISPATCH_LEVEL.

</dd>
</dl>

### -param LocalAddress [in]

A pointer to a buffer that contains the local transport address on which the incoming connection
     arrived. The buffer contains the specific SOCKADDR structure type that corresponds to the address family
     that the WSK application specified when it created the listening socket.


### -param RemoteAddress [in]

A pointer to a buffer that contains the remote transport address from which the incoming
     connection originated. The buffer contains the specific SOCKADDR structure type that corresponds to the
     address family that the WSK application specified when it created the listening socket.


### -param AcceptSocket [in, optional]

A pointer to a 
     <a href="netvista.wsk_socket">WSK_SOCKET</a> structure that is the socket object
     for the accepted socket. If this pointer is <b>NULL</b>, the listening socket is no longer functional and the
     WSK application must call the 
     <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
     listening socket as soon as possible.


### -param AcceptSocketContext [out]

A pointer to a variable that receives a pointer to a WSK application-supplied context for the
     socket that is being accepted. The WSK subsystem passes this pointer to the accepted socket's event
     callback functions. The context information is opaque to the WSK subsystem and must be stored in
     non-paged memory. If the WSK application will not be enabling any event callback functions on the
     accepted socket, the application should set the variable that is pointed to by the 
     <i>AcceptSocketContext</i> parameter to <b>NULL</b>.


### -param AcceptSocketDispatch [out]

A pointer to a variable that receives a pointer to a constant 
     <a href="netvista.wsk_client_connection_dispatch">
     WSK_CLIENT_CONNECTION_DISPATCH</a> structure. This structure is a dispatch table that contains
     pointers to the event callback functions for the accepted socket. If the WSK application will not be
     enabling all of the event callback functions for the accepted socket, the application should set the
     pointers in the dispatch table to <b>NULL</b> for those event callback functions that it does not enable. If
     the WSK application will not be enabling any event callback functions on the accepted socket, it should
     set the variable that is pointed to by the 
     <i>AcceptSocketDispatch</i> parameter to <b>NULL</b>.


## -returns
A WSK application's 
     <i>WskAcceptEvent</i> event callback function can return one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The WSK application accepted the incoming connection.
<dl>
<dt><b>STATUS_REQUEST_NOT_ACCEPTED</b></dt>
</dl>The WSK application rejected the incoming connection. If this value is returned, the WSK
       subsystem will close the accepted socket on behalf of the WSK application.

 


## -remarks
The WSK subsystem calls a WSK application's 
    <i>WskAcceptEvent</i> event callback function when an incoming connection is accepted on the listening
    socket only if the event callback function was previously enabled with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a> socket option.
    For more information about enabling a socket's event callback functions, see 
    <a href="netvista.enabling_and_disabling_event_callback_functions">Enabling and
    Disabling Event Callback Functions</a>.

If a WSK application's 
    <i>WskAcceptEvent</i> event callback function is enabled on a listening socket and the application has a
    pending call to the 
    <a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a> function on the same listening socket,
    then, when an incoming connection arrives, the pending call to 
    <b>WskAccept</b> takes precedence over the 
    <i>WskAcceptEvent</i> event callback function. The WSK subsystem calls the application's 
    <i>WskAcceptEvent</i> event callback function only if there are no IRPs queued from pending calls to the 
    <b>WskAccept</b> function. However, a WSK application should not assume that the WSK subsystem will not
    call the application's 
    <i>WskAcceptEvent</i> event callback function for a listening socket that has a pending call to the 
    <b>WskAccept</b> function. Race conditions exist where the WSK subsystem could still call the WSK
    application's 
    <i>WskAcceptEvent</i> event callback function for the socket. The only way for a WSK application to ensure
    that the WSK subsystem will not call the application's 
    <i>WskAcceptEvent</i> event callback function for a listening socket is to disable the application's 
    <i>WskAcceptEvent</i> event callback function on the socket.

When the WSK subsystem calls a WSK application's 
    <i>WskAcceptEvent</i> event callback function, all of the event callback functions on the accepted socket
    are disabled by default. If a WSK application enables any of the connection-oriented socket event
    callback functions on a listening socket, those event callback functions will be enabled by default on
    all connection-oriented sockets that are accepted on that listening socket. For more information about
    enabling any of the accepted socket's event callback functions, see 
    <a href="netvista.enabling_and_disabling_event_callback_functions">Enabling and
    Disabling Event Callback Functions</a>.

The 
    <a href="netvista.sockaddr">SOCKADDR</a> structures that are pointed to by the 
    <i>LocalAddress</i> and 
    <i>RemoteAddress</i> parameters are valid only for the duration of the call to the 
    <i>WskAcceptEvent</i> event callback function. If a WSK application needs these transport addresses at a
    later time, it can copy the contents of these structures to its own SOCKADDR structures before returning
    from the 
    <i>WskAcceptEvent</i> event callback function, or it can later call the 
    <a href="..\wsk\nc-wsk-pfn_wsk_get_local_address.md">WskGetLocalAddress</a> and 
    <a href="..\wsk\nc-wsk-pfn_wsk_get_remote_address.md">WskGetRemoteAddress</a> functions on the
    accepted socket.

The WSK subsystem allocates the memory for the socket object structure (
    <a href="netvista.wsk_socket">WSK_SOCKET</a>) for the accepted connection on
    behalf of the WSK application. The WSK subsystem deallocates this memory when the socket is closed.

The WSK subsystem calls a WSK application's 
    <i>WskAcceptEvent</i> event callback function at IRQL &lt;= DISPATCH_LEVEL.

A WSK application's <i>WskAcceptEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.


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
<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_get_local_address.md">WskGetLocalAddress</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_get_remote_address.md">WskGetRemoteAddress</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>
</dt>
<dt>
<a href="netvista.sockaddr">SOCKADDR</a>
</dt>
<dt>
<a href="netvista.wsk_client_connection_dispatch">
   WSK_CLIENT_CONNECTION_DISPATCH</a>
</dt>
<dt>
<a href="netvista.wsk_client_listen_dispatch">WSK_CLIENT_LISTEN_DISPATCH</a>
</dt>
<dt>
<a href="netvista.wsk_socket">WSK_SOCKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20PFN_WSK_ACCEPT_EVENT callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

