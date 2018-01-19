---
UID : NC:wsk.PFN_WSK_LISTEN
title : PFN_WSK_LISTEN
author : windows-driver-content
description : The WskListen function enables a stream socket to listen for incoming connections at the socket's bound address.
old-location : netvista\wsklisten.htm
old-project : netvista
ms.assetid : 854C2DA1-1763-4354-8B9D-9AE0C60D8F31
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WPP_TRIAGE_INFO, *PWPP_TRIAGE_INFO, WPP_TRIAGE_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wsk.h
req.include-header : Wsk.h
req.target-type : Universal
req.target-min-winverclnt : Windows 10, version 1703
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WskListen
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


# PFN_WSK_LISTEN callback function
The <b>WskListen</b> function enables a stream socket to listen for incoming connections at the socket's bound address.

## Syntax

```
PFN_WSK_LISTEN PfnWskListen;

NTSTATUS PfnWskListen(
  PWSK_SOCKET Socket,
  PIRP Irp
)
{...}
```

## Parameters

`Socket`

A pointer to a 
     <a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a> structure that specifies the socket
     object for the stream socket that is listening for an incoming connection. This socket must have previously been bound to a local transport address by calling <a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a>.

`Irp`

A pointer to a caller-allocated IRP that the WSK subsystem uses to complete the listen operation
     asynchronously. For more information about using IRPs with WSK functions, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/using-irps-with-winsock-kernel-functions">Using IRPs with Winsock
     Kernel Functions</a>.


## Return Value

<b>WskListen</b> returns one of the following NTSTATUS codes:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The stream socket listened for an incoming connection successfully. The IRP will be completed with success
       status.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The IRP has been queued by the WSK subsystem, which is waiting for an incoming connection on the
       stream socket.
<dl>
<dt><b>STATUS_FILE_FORCED_CLOSED</b></dt>
</dl>The socket is no longer functional. The IRP will be completed with failure status. The WSK
       application must call the 
       <a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a> function to close the
       socket as soon as possible.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. The IRP will be completed with failure status.

## Remarks

A WSK application can call the <b>WskListen</b> function only on a stream socket that the application previously bound to a local transport address by calling the <a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a> function. Once <b>WskListen</b> is successfully called on a stream socket, the socket is committed to a listening socket flow and can no longer call connection-oriented socket functions.

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

<dl>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_bind.md">WskBind</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_accept.md">WskAccept</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_close_socket.md">WskCloseSocket</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_socket.md">WSK_SOCKET</a>
</dt>
<dt>
<a href="..\wsk\ns-wsk-_wsk_provider_stream_dispatch.md">WSK_PROVIDER_STREAM_DISPATCH</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PFN_WSK_LISTEN callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>