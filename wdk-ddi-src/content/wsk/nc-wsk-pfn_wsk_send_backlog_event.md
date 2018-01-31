---
UID : NC:wsk.PFN_WSK_SEND_BACKLOG_EVENT
title : PFN_WSK_SEND_BACKLOG_EVENT
author : windows-driver-content
description : The WskSendBacklogEvent event callback function notifies a WSK application when the ideal send backlog size changes for a connection-oriented socket.
old-location : netvista\wsksendbacklogevent.htm
old-project : netvista
ms.assetid : e944af6f-6753-48b0-b3f6-0709f24e3ff0
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.wsksendbacklogevent, WskSendBacklogEvent callback function [Network Drivers Starting with Windows Vista], WskSendBacklogEvent, PFN_WSK_SEND_BACKLOG_EVENT, PFN_WSK_SEND_BACKLOG_EVENT, wsk/WskSendBacklogEvent, wskref_9b34fa29-9c3a-4aa2-8ceb-3f637c4902cd.xml
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWNODE_HEADER, WNODE_HEADER"
req.product : Windows 10 or later.
---


# PFN_WSK_SEND_BACKLOG_EVENT callback function
The 
  <i>WskSendBacklogEvent</i> event callback function notifies a WSK application when the ideal send backlog
  size changes for a connection-oriented socket.

## Syntax

```
PFN_WSK_SEND_BACKLOG_EVENT PfnWskSendBacklogEvent;

NTSTATUS PfnWskSendBacklogEvent(
  PVOID SocketContext,
  SIZE_T IdealBacklogSize
)
{...}
```

## Parameters

`SocketContext`

A pointer to the socket context for the connection-oriented socket that is notifying the WSK
     application about a change to its ideal send backlog size. The WSK application provided this pointer to
     the WSK subsystem in one of the following ways:
     
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

`IdealBacklogSize`

A variable that contains the new ideal send backlog size.


## Return Value

A WSK application's 
     <i>WskSendBacklogEvent</i> event callback function must always return STATUS_SUCCESS.

## Remarks

The WSK subsystem calls a WSK application's 
    <i>WskSendBacklogEvent</i> event callback function when the ideal send backlog size changes for a
    connection-oriented socket only if the event callback function was previously enabled with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570834">SO_WSK_EVENT_CALLBACK</a> socket option.
    For more information about enabling a socket's event callback functions, see 
    <mshelp:link keywords="netvista.enabling_and_disabling_event_callback_functions" tabindex="0">Enabling and
    Disabling Event Callback Functions</mshelp:link>.

The ideal send backlog size for a connection-oriented socket is the optimal amount of send data that
    needs to be kept outstanding (that is, passed to the WSK subsystem but not yet completed) to keep the
    socket's data stream full at all times. A WSK application can use this size to incrementally probe and
    lock the buffers of data to be sent based on the underlying connection's flow control state.

A WSK application can obtain the current ideal backlog size for a connection-oriented socket at any
    time by calling the 
    <a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a> function.

The WSK subsystem calls a WSK application's 
    <i>WskSendBacklogEvent</i> event callback function at IRQL &lt;= DISPATCH_LEVEL.

A WSK application's <i>WskSendBacklogEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wsk.h (include Wsk.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="..\wsk\nc-wsk-pfn_wsk_send.md">WskSend</a>

<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>

<a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a>

<a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a>

<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>

<mshelp:link keywords="netvista.wsk_client_connection_dispatch" tabindex="0"><b>
   WSK_CLIENT_CONNECTION_DISPATCH</b></mshelp:link>

<a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_SEND_BACKLOG_EVENT callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>