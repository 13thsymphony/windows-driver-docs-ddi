---
UID: NC.ndkpi.NDK_FN_COMPLETE_CONNECT
title: NDK_FN_COMPLETE_CONNECT
author: windows-driver-content
description: The NdkCompleteConnect (NDK_FN_COMPLETE_CONNECT) function completes an asynchronous connection request.
old-location: netvista\ndk_fn_complete_connect.htm
old-project: NetVista
ms.assetid: 85AD83CE-C00F-4D5A-BCDE-22D1B83201A8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS, PNDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api: NdkCompleteConnect
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

# NDK_FN_COMPLETE_CONNECT callback



## -description
The <i>NdkCompleteConnect</i> (<i>NDK_FN_COMPLETE_CONNECT</i>) function completes an asynchronous connection request.



## -prototype

````
NDK_FN_COMPLETE_CONNECT NdkCompleteConnect;

NTSTATUS NdkCompleteConnect(
  _In_     NDK_CONNECTOR                    *pNdkConnector,
  _In_opt_ NDK_FN_DISCONNECT_EVENT_CALLBACK DisconnectEvent,
  _In_opt_ PVOID                            DisconnectEventContext,
  _In_     NDK_FN_REQUEST_COMPLETION        RequestCompletion,
  _In_opt_ PVOID                            RequestContext
)
{ ... }
````


## -parameters

### -param pNdkConnector [in]

A pointer to an NDK connector object (<a href="netvista.ndk_connector">NDK_CONNECTOR</a>).



### -param DisconnectEvent [in, optional]

An optional disconnect notification callback <i>NdkDisconnectEventCallback</i>  function(<a href="..\ndkpi\nc-ndkpi-ndk_fn_disconnect_event_callback.md">NDK_FN_DISCONNECT_EVENT_CALLBACK</a>) that the provider calls when the peer disconnects.


### -param DisconnectEventContext [in, optional]

A context value to pass back to the <i>NdkDisconnectEventCallback</i> function that is specified in the  <i>DisconnectEvent</i> parameter.


### -param RequestCompletion [in]

A pointer to a request completion callback <i>NdkRequestCompletion</i>  function (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>).


### -param RequestContext [in, optional]

A context value that  the provider passes back to the <i>NdkRequestCompletion</i> function that is specified in the <i>RequestCompletion</i> parameter.


## -returns
The 
     <i>NDK_FN_COMPLETE_CONNECT</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The request was completed successfully.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The request is pending. The provider will call the <i>NdkRequestCompletion</i> function that is specified in the <i>RequestCompletion</i> parameter  to complete the request asynchronously.
<dl>
<dt><b>STATUS_CONNECTION_INVALID</b></dt>
</dl>The request failed because the queue pair is not connecting. 
<dl>
<dt><b>STATUS_CONNECTION_ABORTED</b></dt>
</dl>The accepting peer abandoned the pending connection establishment.
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>The request failed because the connection establishment timed out. This is not an indication of a catastrophic or permanent failure, but it ends connection establishment for this connector.
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. 

 


## -remarks
The <i>NdkCompleteConnect</i> function completes a connection request that was  initiated by a previous call to the <i>NdkConnect</i>  (<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect.md">NDK_FN_CONNECT</a>) function. The NDK consumer calls <i>NdkCompleteConnect</i> after the peer accepts the connection request.


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
<a href="netvista.ndk_connector">NDK_CONNECTOR</a>
</dt>
<dt>
<a href="netvista.ndk_connector_dispatch">NDK_CONNECTOR_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect.md">NDK_FN_CONNECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_disconnect_event_callback.md">NDK_FN_DISCONNECT_EVENT_CALLBACK</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>
</dt>
<dt>
<a href="netvista.ndkpi_object_lifetime_requirements">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDK_FN_COMPLETE_CONNECT callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

