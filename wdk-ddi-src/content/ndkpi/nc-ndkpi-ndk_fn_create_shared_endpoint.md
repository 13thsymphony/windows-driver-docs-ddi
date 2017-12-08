---
UID: NC.ndkpi.NDK_FN_CREATE_SHARED_ENDPOINT
title: NDK_FN_CREATE_SHARED_ENDPOINT
author: windows-driver-content
description: The NdkCreateSharedEndpoint (NDK_FN_CREATE_SHARED_ENDPOINT) function creates an NDK shared endpoint.
old-location: netvista\ndk_fn_create_shared_endpoint.htm
old-project: netvista
ms.assetid: FE65B384-387E-4E04-8CF4-9C218F83A0C8
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
req.alt-api: NdkCreateSharedEndpoint
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

# NDK_FN_CREATE_SHARED_ENDPOINT callback



## -description
The <i>NdkCreateSharedEndpoint</i> (<i>NDK_FN_CREATE_SHARED_ENDPOINT</i>) function creates an NDK shared endpoint.


## -prototype

````
NDK_FN_CREATE_SHARED_ENDPOINT NdkCreateSharedEndpoint;

NTSTATUS NdkCreateSharedEndpoint(
  _In_     NDK_ADAPTER                                     *pNdkAdapter,
           _In_reads_bytes_(AddressLength) const PSOCKADDR pAddress,
  _In_     ULONG                                           AddressLength,
  _In_     NDK_FN_CREATE_COMPLETION                        CreateCompletion,
  _In_opt_ PVOID                                           RequestContext,
           _Outptr_ NDK_SHARED_ENDPOINT                    **ppNdkSharedEndpoint
)
{ ... }
````


## -parameters

### -param pNdkAdapter [in]

A pointer to an NDK adapter object (<a href="netvista.ndk_adapter">NDK_ADAPTER</a>).

### -param pAddress 

A local address to use for initiating outgoing connections. For AF_INET or AF_INET6 <i>pAddress</i> contains the local IP address and local ND port.



### -param AddressLength [in]

The size, in bytes, of local address data at the <i>pAddress</i> parameter.



### -param CreateCompletion [in]

A pointer to an <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that completes the creation of an NDK object.

### -param RequestContext [in, optional]

A context value that the NDK provider passes back to the <i>NdkCreateCompletion</i> function that is specified in the <i>CreateCompletion</i> parameter.

### -param ppNdkSharedEndpoint 

A pointer to a created shared endpoint object (<a href="netvista.ndk_shared_endpoint">NDK_SHARED_ENDPOINT</a>) is returned in this location if the request succeeds without returning STATUS_PENDING. If the request returns STATUS_PENDING then this parameter is ignored and the created object is returned with the callback that is specified in the  <i>CreateCompletion</i> parameter.

## -returns
The 
     <i>NdkCreateSharedEndpoint</i> function returns one of the following NTSTATUS codes.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The shared endpoint object was  created successfully and returned with the <i>*ppNdkSharedEndpoint</i> parameter.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl> The operation is pending and will be completed later. The provider will call the function specified in the <i>CreateCompletion</i> parameter (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) to complete the pending operation.
 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The request failed due to insufficient resources. 
<dl>
<dt><b>STATUS_SHARING_VIOLATION</b></dt>
</dl>	  The request failed because the specified local address is already in use.
<dl>
<dt><b>STATUS_TOO_MANY_ADDRESSES</b></dt>
</dl>The request failed because the consumer specified a local port number of zero, and the Network Direct provider was unable to allocate a port from the ephemeral port space (ports 49152-65535.)
<dl>
<dt><b>STATUS_INVALID_ADDRESS</b></dt>
</dl>	The request failed because the specified local address is not a valid address for the adapter. 
<dl>
<dt><b>Other status codes</b></dt>
</dl>An error occurred. 

 

## -remarks
The <i>NdkCreateSharedEndpoint</i> function creates an NDK shared endpoint to use as the local address for multiple outgoing connections that are destined to different remote addresses. This is analogous to having multiple incoming connections to the same local address that are represented by a listener object.

 If the function returns STATUS_SUCCESS, the created object is returned in the <i>ppNdkSharedEndpoint</i> parameter. If <i>NdkCreateSharedEndpoint</i> returns STATUS_PENDING, the created object is returned by the <i>NdkCreateCompletion</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>) function that is specified in the <i>CreateCompletion</i> parameter.

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
<a href="netvista.ndk_adapter">NDK_ADAPTER</a>
</dt>
<dt>
<a href="netvista.ndk_adapter_dispatch">NDK_ADAPTER_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>
</dt>
<dt>
<a href="netvista.ndk_shared_endpoint">NDK_SHARED_ENDPOINT</a>
</dt>
<dt>
<a href="netvista.ndkpi_object_lifetime_requirements">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CREATE_SHARED_ENDPOINT callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
