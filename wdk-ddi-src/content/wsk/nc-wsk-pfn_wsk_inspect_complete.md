---
UID: NC.wsk.PFN_WSK_INSPECT_COMPLETE
title: PFN_WSK_INSPECT_COMPLETE
author: windows-driver-content
description: The WskInspectComplete function completes the inspection of a previously pended incoming connection request that was received on a listening socket that has conditional accept mode enabled.
old-location: netvista\wskinspectcomplete.htm
old-project: netvista
ms.assetid: 31846ec9-0a4b-4e1f-9c14-c1b139f39c55
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WskInspectComplete
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

# PFN_WSK_INSPECT_COMPLETE callback



## -description
The 
  <b>WskInspectComplete</b> function completes the inspection of a previously pended incoming connection
  request that was received on a listening socket that has conditional accept mode enabled.


## -prototype

````
NTSTATUS WSKAPI * WskInspectComplete(
  _In_    PWSK_SOCKET        ListenSocket,
  _In_    PWSK_INSPECT_ID    InspectID,
  _In_    WSK_INSPECT_ACTION Action,
  _Inout_ PIRP               Irp
);
````


## -parameters

### -param ListenSocket [in]

A pointer to a 
     <a href="netvista.wsk_socket">WSK_SOCKET</a> structure. This pointer specifies the
     listening socket on which the WSK application received the incoming connection request that it is
     inspecting.

### -param InspectID [in]

A pointer to a 
     <a href="netvista.wsk_inspect_id">WSK_INSPECT_ID</a> structure. The contents of
     the structure identify the specific connection request that the WSK application is inspecting.

### -param Action [in]

A value that specifies whether the WSK application accepts or rejects the incoming connection
     request. A WSK application must specify either 
     <b>WskInspectAccept</b> or 
     <b>WskInspectReject</b> for this parameter.

### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the resume operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="netvista.using_irps_with_winsock_kernel_functions">Using IRPs with Winsock
     Kernel Functions</a>.

## -returns
<b>WskInspectComplete</b> returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The previously pended inspect operation was successfully resumed. The IRP will be completed with
       success status.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The WSK subsystem could not resume the inspect operation immediately. The WSK subsystem will
       complete the IRP after it has resumed the inspect operation of the incoming connection request. The
       status of resuming the inspect operation will be returned in the 
       <b>IoStatus.Status</b> field of the IRP.
<dl>
<dt><b>STATUS_FILE_FORCED_CLOSED</b></dt>
</dl>The socket is no longer functional. The IRP will be completed with failure status. The WSK
       application must call the 
       <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
       socket as soon as possible.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. The IRP will be completed with failure status.

 

## -remarks
A WSK application calls the 
    <b>WskInspectComplete</b> function to complete the inspection of an incoming connection request for which
    the application's 
    <a href="..\wsk\nc-wsk-pfn_wsk_inspect_event.md">WskInspectEvent</a> event callback function
    previously returned 
    <b>WskInspectPend</b>.

A WSK application can call the 
    <b>WskInspectComplete</b> function only on a listening socket that has conditional accept mode enabled. A
    WSK application can enable conditional accept mode on a listening socket by enabling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a> socket option.
    For more information about conditionally accepting incoming connections, see 
    <a href="netvista.listening_for_and_accepting_incoming_connections">Listening for and
    Accepting Incoming Connections</a>.

The WSK subsystem passed a pointer to a 
    <a href="netvista.wsk_inspect_id">WSK_INSPECT_ID</a> structure to the WSK
    application when it called the application's 
    <i>WskInspectEvent</i> event callback function. The WSK application copied the contents of that structure
    to its own WSK_INSPECT_ID structure before returning 
    <b>WskInspectPend</b> from the 
    <i>WskInspectEvent</i> event callback function. The WSK application passes a pointer to its own
    WSK_INSPECT_ID structure in the 
    <i>InspectID</i> parameter when it calls the 
    <b>WskInspectComplete</b> function.

If a WSK application specifies 
    <b>WskInspectAccept</b> in the 
    <i>Action</i> parameter, the WSK subsystem will continue to establish the socket connection. The WSK
    subsystem will return the socket to the WSK application by either completing a call by the WSK
    application to the 
    <a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a> function or calling the WSK
    application's 
    <a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a> event callback function if
    it is enabled. If the incoming connection request is dropped before the socket connection is fully
    established, the WSK subsystem will call the WSK application's 
    <a href="..\wsk\nc-wsk-pfn_wsk_abort_event.md">WskAbortEvent</a> event callback function.

If a WSK application specifies 
    <b>WskInspectReject</b> in the 
    <i>Action</i> parameter, the incoming connection request is dropped, and the socket connection is not
    established.

If the incoming connection request is dropped by the remote system before the WSK application calls
    the 
    <b>WskInspectComplete</b> function, the WSK subsystem calls the WSK application's 
    <i>WskAbortEvent</i> event callback function.

If the WSK application calls the 
    <b>WskInspectComplete</b> function on an incoming connection request that has been aborted, the connection
    will not be established even if the WSK application specified 
    <b>WskInspectAccept</b> in the 
    <i>Action</i> parameter.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
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
<a href="..\wsk\nc-wsk-pfn_wsk_abort_event.md">WskAbortEvent</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_accept_event.md">WskAcceptEvent</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_inspect_event.md">WskInspectEvent</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570829">SO_CONDITIONAL_ACCEPT</a>
</dt>
<dt>
<a href="netvista.wsk_inspect_id">WSK_INSPECT_ID</a>
</dt>
<dt>
<a href="netvista.wsk_provider_listen_dispatch">WSK_PROVIDER_LISTEN_DISPATCH</a>
</dt>
<dt>
<a href="netvista.wsk_socket">WSK_SOCKET</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_INSPECT_COMPLETE callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
