---
UID: NC:ndkpi.NDK_FN_DISCONNECT
title: NDK_FN_DISCONNECT
author: windows-driver-content
description: The NdkDisconnect (NDK_FN_DISCONNECT) function starts a disconnect on an NDK connection.
old-location: netvista\ndk_fn_disconnect.htm
old-project: netvista
ms.assetid: 40622358-F4CA-4DF2-BDA4-E93C4DDB1AF6
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api: NdkDisconnect
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
req.typenames: NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
---

# NDK_FN_DISCONNECT callback



## -description
The <i>NdkDisconnect</i> (<i>NDK_FN_DISCONNECT</i>) function starts a  disconnect on an NDK connection.



## -prototype

````
NDK_FN_DISCONNECT NdkDisconnect;

NTSTATUS NdkDisconnect(
  _In_     NDK_CONNECTOR             *pNdkConnector,
  _In_     NDK_FN_REQUEST_COMPLETION RequestCompletion,
  _In_opt_ PVOID                     RequestContext
)
{ ... }
````


## -parameters

### -param pNdkConnector [in]

A pointer to a connector object (<a href="..\ndkpi\ns-ndkpi-_ndk_connector.md">NDK_CONNECTOR</a>).


### -param RequestCompletion [in]

A pointer to a request completion callback routine <i>NdkRequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>).


### -param RequestContext [in, optional]

A context value to pass to the <i>Context</i> parameter of the  callback function that is specified in the <i>RequestCompletion</i> parameter.


## -returns
The <i>NdkDisconnect</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The disconnect request was completed successfully.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl> The operation is pending and will be completed later. The driver will call the specified <i>RequestCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>) function to complete the pending operation.
 
<dl>
<dt><b>STATUS_IO_TIMEOUT</b></dt>
</dl>The disconnect handshake timed out. 
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred.

 


## -remarks
<i>NdkDisconnect</i> initiates a graceful disconnect on a connection. After the underlying protocol driver performs a graceful disconnect, the NDK provider must also perform an implicit flush on the QP.


## -see-also
<dl>
<dt>
<a href="..\ndkpi\ns-ndkpi-_ndk_connector_dispatch.md">NDK_CONNECTOR_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect.md">NDK_FN_CONNECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_request_completion.md">NDK_FN_REQUEST_COMPLETION</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/94993523-D0D7-441E-B95C-417800840BAC">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_DISCONNECT callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

