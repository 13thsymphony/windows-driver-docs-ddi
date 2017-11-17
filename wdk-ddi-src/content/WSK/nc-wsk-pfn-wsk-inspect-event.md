---
UID: NC.wsk.PFN_WSK_INSPECT_EVENT
title: PFN_WSK_INSPECT_EVENT
author: windows-driver-content
description: The WskInspectEvent event callback function notifies a WSK application that an incoming connection request on a listening socket that has conditional accept mode enabled has been received.
old-location: netvista\wskinspectevent.htm
ms.assetid: 40f184ac-4ef3-485a-a529-71c1f2716427
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: netvista
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating
   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WskInspectEvent
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
ms.keywords: WPP_TRIAGE_INFO, WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO
req.iface: 
req.product: Windows 10 or later.
---

# PFN_WSK_INSPECT_EVENT callback



## -description
<p>The 
  <i>WskInspectEvent</i> event callback function notifies a WSK application that an incoming connection
  request on a listening socket that has conditional accept mode enabled has been received.</p>


## -prototype

````
PFN_WSK_INSPECT_EVENT WskInspectEvent;

WSK_INSPECT_ACTION APIENTRY WskInspectEvent(
  _In_opt_ PVOID           SocketContext,
  _In_     PSOCKADDR       LocalAddress,
  _In_     PSOCKADDR       RemoteAddress,
  _In_opt_ PWSK_INSPECT_ID InspectID
)
{ ... }
````


## -parameters
<dl>

### -param <i>SocketContext</i> [in, optional]

<dd>
<p>A pointer to the socket context for the listening socket on which the incoming connection request
     was received. The WSK application provided this pointer to the WSK subsystem when it called the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> function to create the listening
     socket.</p>
</dd>

### -param <i>LocalAddress</i> [in]

<dd>
<p>A pointer to a buffer that contains the local transport address on which the incoming connection
     request arrived. The buffer contains the specific SOCKADDR structure type that corresponds to the
     address family that the WSK application specified when it created the listening socket.</p>
</dd>

### -param <i>RemoteAddress</i> [in]

<dd>
<p>A pointer to a buffer that contains the remote transport address from which the incoming
     connection request originated. The buffer contains the specific SOCKADDR structure type that corresponds
     to the address family that the WSK application specified when it created the listening socket.</p>
</dd>

### -param <i>InspectID</i> [in, optional]

<dd>
<p>A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571170">WSK_INSPECT_ID</a> structure. The contents of
     the structure identify the incoming connection request that is being inspected. If this pointer is <b>NULL</b>,
     the listening socket is no longer functional and the WSK application must call the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a> function to close the
     listening socket as soon as possible.</p>
</dd>
</dl>

## -returns
<p>A WSK application's 
     <i>WskInspectEvent</i> event callback function can return one of the following WSK_INSPECT_ACTION
     values:</p><dl>
<dt><b><b>WskInspectAccept</b></b></dt>
</dl><p>The incoming connection request is accepted.</p><dl>
<dt><b><b>WskInspectReject</b></b></dt>
</dl><p>The incoming connection request is rejected.</p><dl>
<dt><b><b>WskInspectPend</b></b></dt>
</dl><p>The WSK application could not determine if the incoming connection request should be accepted or
       rejected immediately.</p>

<p> </p>

## -remarks
<p>The WSK subsystem calls a WSK application's 
    <i>WskInspectEvent</i> event callback function on a listening socket that has conditional accept mode
    enabled. A WSK application can enable conditional accept mode on a listening socket by enabling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a> socket option.
    For more information about conditionally accepting incoming connections, see 
    <a href="netvista.listening_for_and_accepting_incoming_connections">Listening for and
    Accepting Incoming Connections</a>.</p>

<p>If a WSK application returns 
    <b>WskInspectAccept</b> from its 
    <i>WskInspectEvent</i> event callback function, the WSK subsystem continues to establish the socket
    connection. The WSK subsystem returns the socket to the WSK application by either completing a call to
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a> function, or by calling the WSK
    application's 
    <a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a> event callback function if
    the event callback function is enabled. If the incoming connection request is dropped before the socket
    connection is fully established, the WSK subsystem calls the WSK application's 
    <a href="https://msdn.microsoft.com/50e0ef5d-0577-4b5c-b541-fc78079a953c">WskAbortEvent</a> event callback function.</p>

<p>If a WSK application returns 
    <b>WskInspectReject</b> from its 
    <i>WskInspectEvent</i> event callback function, the incoming connection request is dropped and the socket
    connection is not established.</p>

<p>If a WSK application returns 
    <b>WskInspectPend</b> from its 
    <i>WskInspectEvent</i> event callback function, the application must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571136">WskInspectComplete</a> function after it
    has determined whether the incoming connection request should be accepted or rejected (unless the
    incoming connection request is aborted in the meantime). The WSK application must copy the contents of
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571170">WSK_INSPECT_ID</a> structure that is pointed to
    by the 
    <i>InspectID</i> parameter to its own WSK_INSPECT_ID structure before returning from the 
    <i>WskInspectEvent</i> event callback function. The WSK application passes a pointer to its own
    WSK_INSPECT_ID structure to the 
    <b>WskInspectComplete</b> function when it completes the inspection. The WSK application also uses this
    structure to identify the incoming connection request if the request is aborted before the inspection is
    complete.</p>

<p>The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a> structures that are pointed to by the 
    <i>LocalAddress</i> and 
    <i>RemoteAddress</i> parameters are valid only for the duration of the call to the 
    <i>WskInspectEvent</i> event callback function. If a WSK application returns 
    <b>WskInspectPend</b> from its 
    <i>WskInspectEvent</i> event callback function and it needs these transport addresses during the remainder
    of the inspection, it must copy the contents of these structures to its own SOCKADDR structures before
    returning from the 
    <i>WskInspectEvent</i> event callback function.</p>

<p>The WSK subsystem calls a WSK application's 
    <i>WskInspectEvent</i> event callback function at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>A WSK application's <i>WskInspectEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.</p>

<p>The WSK subsystem calls a WSK application's 
    <i>WskInspectEvent</i> event callback function on a listening socket that has conditional accept mode
    enabled. A WSK application can enable conditional accept mode on a listening socket by enabling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a> socket option.
    For more information about conditionally accepting incoming connections, see 
    <a href="netvista.listening_for_and_accepting_incoming_connections">Listening for and
    Accepting Incoming Connections</a>.</p>

<p>If a WSK application returns 
    <b>WskInspectAccept</b> from its 
    <i>WskInspectEvent</i> event callback function, the WSK subsystem continues to establish the socket
    connection. The WSK subsystem returns the socket to the WSK application by either completing a call to
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a> function, or by calling the WSK
    application's 
    <a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a> event callback function if
    the event callback function is enabled. If the incoming connection request is dropped before the socket
    connection is fully established, the WSK subsystem calls the WSK application's 
    <a href="https://msdn.microsoft.com/50e0ef5d-0577-4b5c-b541-fc78079a953c">WskAbortEvent</a> event callback function.</p>

<p>If a WSK application returns 
    <b>WskInspectReject</b> from its 
    <i>WskInspectEvent</i> event callback function, the incoming connection request is dropped and the socket
    connection is not established.</p>

<p>If a WSK application returns 
    <b>WskInspectPend</b> from its 
    <i>WskInspectEvent</i> event callback function, the application must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571136">WskInspectComplete</a> function after it
    has determined whether the incoming connection request should be accepted or rejected (unless the
    incoming connection request is aborted in the meantime). The WSK application must copy the contents of
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571170">WSK_INSPECT_ID</a> structure that is pointed to
    by the 
    <i>InspectID</i> parameter to its own WSK_INSPECT_ID structure before returning from the 
    <i>WskInspectEvent</i> event callback function. The WSK application passes a pointer to its own
    WSK_INSPECT_ID structure to the 
    <b>WskInspectComplete</b> function when it completes the inspection. The WSK application also uses this
    structure to identify the incoming connection request if the request is aborted before the inspection is
    complete.</p>

<p>The 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a> structures that are pointed to by the 
    <i>LocalAddress</i> and 
    <i>RemoteAddress</i> parameters are valid only for the duration of the call to the 
    <i>WskInspectEvent</i> event callback function. If a WSK application returns 
    <b>WskInspectPend</b> from its 
    <i>WskInspectEvent</i> event callback function and it needs these transport addresses during the remainder
    of the inspection, it must copy the contents of these structures to its own SOCKADDR structures before
    returning from the 
    <i>WskInspectEvent</i> event callback function.</p>

<p>The WSK subsystem calls a WSK application's 
    <i>WskInspectEvent</i> event callback function at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>A WSK application's <i>WskInspectEvent</i> event callback function must not wait for completion of other WSK requests in the context of WSK completion or event callback functions. The callback can initiate other WSK requests (assuming that it doesn't spend too much time at DISPATCH_LEVEL), but it must not wait for their completion even when the callback is called at IRQL = PASSIVE_LEVEL.</p>

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
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571109">WskAccept</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571124">WskCloseSocket</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571127">WskControlSocket</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571136">WskInspectComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/50e0ef5d-0577-4b5c-b541-fc78079a953c">WskAbortEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/672440f0-810a-4e68-82a5-d038770898c5">WskAcceptEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570822">SOCKADDR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571162">WSK_CLIENT_LISTEN_DISPATCH</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff571170">WSK_INSPECT_ID</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_INSPECT_EVENT callback function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
