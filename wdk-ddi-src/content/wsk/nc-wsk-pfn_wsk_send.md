---
UID: NC.wsk.PFN_WSK_SEND
title: PFN_WSK_SEND
author: windows-driver-content
description: The WskSend function sends data over a connection-oriented or stream socket to a remote transport address.
old-location: netvista\wsksend.htm
old-project: netvista
ms.assetid: 40fe1e3b-22b2-4d78-a306-977188246935
ms.author: windowsdriverdev
ms.date: 12/8/2017
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
req.alt-api: WskSend
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

# PFN_WSK_SEND callback



## -description
The 
  <b>WskSend</b> function sends data over a connection-oriented or stream socket to a remote transport address.



## -prototype

````
NTSTATUS WSKAPI * WskSend(
  _In_    PWSK_SOCKET Socket,
  _In_    PWSK_BUF    Buffer,
  _In_    ULONG       Flags,
  _Inout_ PIRP        Irp
);
````


## -parameters

### -param Socket [in]

A pointer to a 
     <a href="netvista.wsk_socket">WSK_SOCKET</a> structure that specifies the socket
     object for the socket over which to send the data.


### -param Buffer [in]

A pointer to an initialized 
     <a href="netvista.wsk_buf">WSK_BUF</a> structure that describes the data buffer
     that contains the data that is being sent over the socket.


### -param Flags [in]

A ULONG value that contains a bitwise OR of a combination of the following flags:
     




### -param WSK_FLAG_NODELAY

Directs the underlying transport to immediately send the data, and any previously queued data,
       to the remote application without delay.
       

This flag is supported by the Microsoft TCP/IP transport protocol. This flag might not be supported
       by other transport protocols.

</dd>
</dl>

### -param Irp [in, out]

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the send operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="netvista.using_irps_with_winsock_kernel_functions">Using IRPs with Winsock
     Kernel Functions</a>.


## -returns
<b>WskSend</b> returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>Data was successfully sent over the socket. The IRP will be completed with success status. The 
       <b>IoStatus.Information</b> field of the IRP contains the number of bytes that were sent.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The WSK subsystem could not send the data over the socket immediately. The WSK subsystem will
       complete the IRP after it has sent the data over the socket. The status of the send operation will be
       returned in the 
       <b>IoStatus.Status</b> field of the IRP. If the operation succeeds, the 
       <b>IoStatus.Information</b> field of the IRP will contain the number of bytes that were sent.
<dl>
<dt><b>STATUS_FILE_FORCED_CLOSED</b></dt>
</dl>The socket is no longer functional. The IRP will be completed with failure status. The WSK
       application must call the 
       <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
       socket as soon as possible.
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>A specified flag is not supported by the underlying network transport.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. The IRP will be completed with failure status.

 


## -remarks
A WSK application can call the 
    <b>WskSend</b> function only on a connection-oriented or stream socket that has been previously connected to a
    remote transport address. A connection-oriented socket is connected to a remote transport address by one
    of the following methods:

The WSK application connects the socket by calling the 
      <a href="..\wsk\nc-wsk-pfn_wsk_connect.md">WskConnect</a> function.

The WSK application creates, binds, and connects the socket by calling the 
      <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function.

The WSK subsystem connects the socket when the WSK application accepts an incoming connection
      request on a listening socket.

If the 
    <b>WskSend</b> function returns STATUS_PENDING, the MDL chain that is described in the 
    <a href="netvista.wsk_buf">WSK_BUF</a> structure that is pointed to by the 
    <i>Buffer</i> parameter must remain locked in memory until the IRP is completed.

The WSK subsystem does not perform any buffering of data when it sends data over a socket. Therefore,
    a call to the 
    <b>WskSend</b> function will not be completed by the WSK subsystem until all of the data has actually been
    sent.


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
<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_receive.md">WskReceive</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_receive_event.md">WskReceiveEvent</a>
</dt>
<dt>
<a href="netvista.wsk_buf">WSK_BUF</a>
</dt>
<dt>
<a href="netvista.wsk_provider_connection_dispatch">
   WSK_PROVIDER_CONNECTION_DISPATCH</a>
</dt>
<dt>
<a href="netvista.wsk_provider_stream_dispatch">WSK_PROVIDER_STREAM_DISPATCH</a>
</dt>
<dt>
<a href="netvista.wsk_socket">WSK_SOCKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_SEND callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

