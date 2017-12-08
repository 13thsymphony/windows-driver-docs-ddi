---
UID: NC.ndkpi.NDK_FN_ACCEPT
title: NDK_FN_ACCEPT
author: windows-driver-content
description: The NdkAccept (NDK_FN_ACCEPT) function accepts an incoming connection request over a listener object.
old-location: netvista\ndk_fn_accept.htm
old-project: netvista
ms.assetid: 1010F6AD-2D2F-46E5-816E-C5CE68ED11CF
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdkAccept
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# NDK_FN_ACCEPT callback



## -description
The <i>NdkAccept</i> (<i>NDK_FN_ACCEPT</i>) function accepts  an incoming connection request over a listener object.


## -prototype

````
NDK_FN_ACCEPT NdkAccept;

NTSTATUS NdkAccept(
  _In_     NDK_CONNECTOR                                       *pNdkConnector,
  _In_     NDK_QP                                              *pNdkQp,
  _In_     ULONG                                               InboundReadLimit,
  _In_     ULONG                                               OutboundReadLimit,
           _In_reads_bytes_opt_(PrivateDataLength) CONST PVOID pPrivateData,
  _In_     ULONG                                               PrivateDataLength,
  _In_opt_ NDK_FN_DISCONNECT_EVENT_CALLBACK                    DisconnectEvent,
  _In_opt_ PVOID                                               DisconnectEventContext,
  _In_     NDK_FN_REQUEST_COMPLETION                           RequestCompletion,
  _In_opt_ PVOID                                               RequestContext
)
{ ... }
````


## -parameters

### -param pNdkConnector [in]

A pointer to an NDK connector object (<a href="netvista.ndk_connector">NDK_CONNECTOR</a>).

### -param pNdkQp [in]

A pointer to an NDK queue pair (QP) object (<a href="netvista.ndk_qp">NDK_QP</a>) to associate with the connection.

### -param InboundReadLimit [in]

The consumer-supplied maximum number of incoming in-progress read operations to allow on the QP. If the underlying provider has a lower <b>MaxInboundReadLimit</b> value in the <a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a> structure, then the provider will cap the consumer-supplied value to the provider maximum. If the peer has a lower <i>OutboundReadLimit</i> value, then the provider will use that value as the effective <i>InboundReadLimit</i>. The consumer can retrieve the effective <i>InboundReadLimit</i> by calling the <i>NdkGetConnectionData</i> function (<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_connection_data.md">NDK_FN_GET_CONNECTION_DATA</a>).

### -param OutboundReadLimit [in]

The consumer-supplied maximum number of outgoing in-progress read operations to allow on the QP. If the underlying provider has a lower <b>MaxOutboundReadLimit</b> value  in the <a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a> structure, then the provider will cap the consumer supplied value to the provider maximum. If the peer has a lower <i>InboundReadLimit</i>, then the provider will use that value as the effective <i>OutboundReadLimit</i>. The     consumer can retrieve the effective <i>OutboundReadLimit</i> by calling the <i>NdkGetConnectionData</i> function (<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_connection_data.md">NDK_FN_GET_CONNECTION_DATA</a>).

### -param pPrivateData 

A pointer to private data that is sent back with the accept request.

### -param PrivateDataLength [in]

The length, in bytes, of the private data that is provided in the <i>pPrivateData</i> parameter.

### -param DisconnectEvent [in, optional]

An entry point for an optional disconnect notification callback function <i>NdkDisconnectEventCallback</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_disconnect_event_callback.md">NDK_FN_DISCONNECT_EVENT_CALLBACK</a>). The provider calls this callback function when the peer disconnects.

### -param DisconnectEventContext [in, optional]

A context value to pass to the <i>DisconnectEventContext</i> parameter of the  callback function that is specified in the <i>DisconnectEvent</i> parameter.

### -param RequestCompletion [in]

A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>).

### -param RequestContext [in, optional]

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.

## -returns
The 
     <i>NDK_FN_ACCEPT</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl> The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 
<dl>
<dt><b>STATUS_CONNECTION_ABORTED</b></dt>
</dl>The connecting peer abandoned the pending connection establishment.
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>The peer did not call the CompleteConnect (<a href="..\ndkpi\nc-ndkpi-ndk_fn_complete_connect.md">NDK_FN_COMPLETE_CONNECT</a>) function to complete the pending connection request. 
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. 

 

## -remarks
The  NDK consumer calls <i>NdkAccept</i> to accept  an incoming connection request over a listener object.

The <i>NdkCreateListener</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_listener.md">NDK_FN_CREATE_LISTENER</a>) function creates an NDK listener object and provides an <i>NdkConnectEventCallback</i> function (<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a>).



The <i>NdkConnectEventCallback</i> function is used by the NDK provider to notify the consumer about each incoming connection request.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
None supported
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported in NDIS 6.30 and later.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndk_adapter_info">NDK_ADAPTER_INFO</a>
</dt>
<dt>
<a href="netvista.ndk_connector">NDK_CONNECTOR</a>
</dt>
<dt>
<a href="netvista.ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_complete_connect.md">NDK_FN_COMPLETE_CONNECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_listener.md">NDK_FN_CREATE_LISTENER</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_disconnect_event_callback.md">NDK_FN_DISCONNECT_EVENT_CALLBACK</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_get_connection_data.md">NDK_FN_GET_CONNECTION_DATA</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_reject.md">NDK_FN_REJECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>
</dt>
<dt>
<a href="netvista.ndk_qp">NDK_QP</a>
</dt>
<dt>
<a href="netvista.ndkpi_object_lifetime_requirements">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_ACCEPT callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
