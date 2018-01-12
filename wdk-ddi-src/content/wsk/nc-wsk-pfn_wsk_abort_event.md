---
UID: NC:wsk.PFN_WSK_ABORT_EVENT
title: PFN_WSK_ABORT_EVENT
author: windows-driver-content
description: The WskAbortEvent event callback function notifies a WSK application that an incoming connection request on a listening socket that has conditional accept mode enabled has been dropped.
old-location: netvista\wskabortevent.htm
old-project: netvista
ms.assetid: 50e0ef5d-0577-4b5c-b541-fc78079a953c
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _WPP_TRIAGE_INFO, WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
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
req.alt-api: WskAbortEvent
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
req.typenames: WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.product: Windows 10 or later.
---

# PFN_WSK_ABORT_EVENT callback



## -description
The 
  <i>WskAbortEvent</i> event callback function notifies a WSK application that an incoming connection request
  on a listening socket that has conditional accept mode enabled has been dropped.



## -prototype

````
PFN_WSK_ABORT_EVENT WskAbortEvent;

NTSTATUS APIENTRY WskAbortEvent(
  _In_opt_ PVOID           SocketContext,
  _In_     PWSK_INSPECT_ID InspectID
)
{ ... }
````


## -parameters

### -param SocketContext [in, optional]

A pointer to the socket context for the listening socket on which the incoming connection request
     was received. The WSK application provided this pointer to the WSK subsystem when it called the 
     <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create the listening
     socket.


### -param InspectID [in]

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_inspect_id.md">WSK_INSPECT_ID</a> structure. The contents of
     the structure identify the incoming connection request that has been dropped.


## -returns
A WSK application's 
     <i>WskAbortEvent</i> event callback function must always return STATUS_SUCCESS.


## -remarks
The WSK subsystem calls a WSK application's 
    <i>WskAbortEvent</i> event callback function only when the following conditions are true:

The WSK application created a listening socket that has conditional accept mode enabled.

An incoming connection request has been received on the listening socket, and the WSK subsystem has
      called the WSK application's 
      <a href="..\wsk\nc-wsk-pfn_wsk_inspect_event.md">WskInspectEvent</a> event callback
      function.

The WSK application returned 
      <b>WskInspectPend</b> or <b>WskInspectAccept</b> from its 
      <i>WskAbortEvent</i> event callback function for the incoming connection request.

The incoming connection request has been dropped either locally or remotely before being fully established.

When the WSK subsystem calls a WSK application's 
    <i>WskAbortEvent</i> event callback function, the application should terminate the inspection for the
    incoming connection request. The connection request is identified by the contents of the 
    <a href="..\wsk\ns-wsk-_wsk_inspect_id.md">WSK_INSPECT_ID</a> structure that is pointed to
    by the 
    <i>InspectID</i> parameter.

If the WSK application calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_inspect_complete.md">WskInspectComplete</a> function on an incoming connection request that has been aborted, the connection
    will not be established even if 
    <b>WskInspectAccept</b> is specified in the 
    <i>Action</i> parameter.

A WSK application can enable conditional accept mode on a listening socket by enabling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a> socket option.
    For more information about conditionally accepting incoming connections, see 
    <a href="netvista.listening_for_and_accepting_incoming_connections">Listening for and
    Accepting Incoming Connections</a>.

The WSK subsystem calls a WSK application's 
    <i>WskAbortEvent</i> event callback function at IRQL &lt;= DISPATCH_LEVEL.

A WSK application's <i>WskAbortEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.


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
<a href="..\wsk\nc-wsk-pfn_wsk_control_socket.md">WskControlSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_inspect_complete.md">WskInspectComplete</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_inspect_event.md">WskInspectEvent</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_client_listen_dispatch.md">WSK_CLIENT_LISTEN_DISPATCH</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_inspect_id.md">WSK_INSPECT_ID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_ABORT_EVENT callback function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

