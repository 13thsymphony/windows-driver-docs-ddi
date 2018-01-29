---
UID : NC:wsk.PFN_WSK_SEND
title : PFN_WSK_SEND
author : windows-driver-content
description : The WskSend function sends data over a connection-oriented or stream socket to a remote transport address.
old-location : netvista\wsksend.htm
old-project : netvista
ms.assetid : 40fe1e3b-22b2-4d78-a306-977188246935
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.wsksend, WskSend callback function [Network Drivers Starting with Windows Vista], WskSend, PFN_WSK_SEND, PFN_WSK_SEND, wsk/WskSend, wskref_978af27f-fa9e-4c21-9940-1d47b3fcb997.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wsk.h
req.include-header : Wsk.h
req.target-type : Universal
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
req.typenames : WNODE_HEADER, *PWNODE_HEADER
req.product : Windows 10 or later.
---


# PFN_WSK_SEND callback function
The 
  <b>WskSend</b> function sends data over a connection-oriented or stream socket to a remote transport address.

## Syntax

```
PFN_WSK_SEND PfnWskSend;

NTSTATUS PfnWskSend(
  PWSK_SOCKET Socket,
  PWSK_BUF Buffer,
  ULONG Flags,
  PIRP Irp
)
{...}
```

## Parameters

`Socket`

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that specifies the socket
     object for the socket over which to send the data.

`Buffer`

A pointer to an initialized 
     <a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a> structure that describes the data buffer
     that contains the data that is being sent over the socket.

`Flags`

A ULONG value that contains a bitwise OR of a combination of the following flags:

`Irp`

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the send operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <mshelp:link keywords="netvista.using_irps_with_winsock_kernel_functions" tabindex="0">Using IRPs with Winsock
     Kernel Functions</mshelp:link>.


## Return Value

<b>WskSend</b> returns one of the following NTSTATUS codes:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Data was successfully sent over the socket. The IRP will be completed with success status. The 
       <b>IoStatus.Information</b> field of the IRP contains the number of bytes that were sent.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The WSK subsystem could not send the data over the socket immediately. The WSK subsystem will
       complete the IRP after it has sent the data over the socket. The status of the send operation will be
       returned in the 
       <b>IoStatus.Status</b> field of the IRP. If the operation succeeds, the 
       <b>IoStatus.Information</b> field of the IRP will contain the number of bytes that were sent.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_FORCED_CLOSED</b></dt>
</dl>
</td>
<td width="60%">
The socket is no longer functional. The IRP will be completed with failure status. The WSK
       application must call the 
       <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
       socket as soon as possible.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
A specified flag is not supported by the underlying network transport.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status codes</b></dt>
</dl>
</td>
<td width="60%">
An error occurred. The IRP will be completed with failure status.

</td>
</tr>
</table>

## Remarks

A WSK application can call the 
    <b>WskSend</b> function only on a connection-oriented or stream socket that has been previously connected to a
    remote transport address. A connection-oriented socket is connected to a remote transport address by one
    of the following methods:
<ul>
<li>
The WSK application connects the socket by calling the 
      <a href="..\wsk\nc-wsk-pfn_wsk_connect.md">WskConnect</a> function.

</li>
<li>
The WSK application creates, binds, and connects the socket by calling the 
      <a href="..\wsk\nc-wsk-pfn_wsk_socket_connect.md">WskSocketConnect</a> function.

</li>
<li>
The WSK subsystem connects the socket when the WSK application accepts an incoming connection
      request on a listening socket.

</li>
</ul>If the 
    <b>WskSend</b> function returns STATUS_PENDING, the MDL chain that is described in the 
    <a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a> structure that is pointed to by the 
    <i>Buffer</i> parameter must remain locked in memory until the IRP is completed.

The WSK subsystem does not perform any buffering of data when it sends data over a socket. Therefore,
    a call to the 
    <b>WskSend</b> function will not be completed by the WSK subsystem until all of the data has actually been
    sent.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wsk.h (include Wsk.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wsk\ns-wsk-_wsk_provider_stream_dispatch.md">WSK_PROVIDER_STREAM_DISPATCH</a>

<mshelp:link keywords="netvista.wsk_provider_connection_dispatch" tabindex="0"><b>
   WSK_PROVIDER_CONNECTION_DISPATCH</b></mshelp:link>

<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>

<a href="..\wsk\nc-wsk-pfn_wsk_receive_event.md">WskReceiveEvent</a>

<a href="..\wsk\nc-wsk-pfn_wsk_receive.md">WskReceive</a>

<a href="..\wsk\ns-wsk-_wsk_buf.md">WSK_BUF</a>

<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_SEND callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>