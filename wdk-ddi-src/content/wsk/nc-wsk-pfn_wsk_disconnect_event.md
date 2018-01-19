---
UID : NC:wsk.PFN_WSK_DISCONNECT_EVENT
title : PFN_WSK_DISCONNECT_EVENT
author : windows-driver-content
description : The WskDisconnectEvent event callback function notifies a WSK application that a connection on a connection-oriented socket has been disconnected by the remote application.
old-location : netvista\wskdisconnectevent.htm
old-project : netvista
ms.assetid : bf12d7b3-080e-46d9-b276-76d42068e7c6
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wsk.h
req.include-header : Wsk.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WskDisconnectEvent
req.alt-loc : wsk.h
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
req.typenames : "*PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO"
req.product : Windows 10 or later.
---


# PFN_WSK_DISCONNECT_EVENT callback function
The 
  <i>WskDisconnectEvent</i> event callback function notifies a WSK application that a connection on a
  connection-oriented socket has been disconnected by the remote application.

## Syntax

```
PFN_WSK_DISCONNECT_EVENT PfnWskDisconnectEvent;

NTSTATUS PfnWskDisconnectEvent(
  PVOID SocketContext,
  ULONG Flags
)
{...}
```

## Parameters

`SocketContext`

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

`Flags`

A ULONG value that contains a bitwise OR of a combination of the following flags:


## Return Value

A WSK application's 
     <i>WskDisconnectEvent</i> event callback function must always return STATUS_SUCCESS.

## Remarks

The WSK subsystem calls a WSK application's 
    <i>WskDisconnectEvent</i> event callback function when a connection-oriented socket is disconnected by the
    remote application only if the event callback function was previously enabled with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a> socket option.
    For more information about enabling a socket's event callback functions, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa363707">Enabling and
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

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wsk.h (include Wsk.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

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
<a href="..\wsk\ns-wsk-_wsk_client_connection_dispatch.md">
   WSK_CLIENT_CONNECTION_DISPATCH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_DISCONNECT_EVENT callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>