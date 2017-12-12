---
UID: NS.NDKPI._NDK_ADAPTER_DISPATCH
title: _NDK_ADAPTER_DISPATCH
author: windows-driver-content
description: The NDK_ADAPTER_DISPATCH structure specifies dispatch function entry points for the NDK adapter object.
old-location: netvista\ndk_adapter_dispatch.htm
old-project: netvista
ms.assetid: 61C425CB-4900-4EB2-8D33-FF235BC03929
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDK_ADAPTER_DISPATCH, NDK_ADAPTER_DISPATCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDK_ADAPTER_DISPATCH
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

# _NDK_ADAPTER_DISPATCH structure



## -description
The <b>NDK_ADAPTER_DISPATCH</b> structure specifies dispatch function entry points for the NDK adapter object.



## -syntax

````
typedef struct _NDK_ADAPTER_DISPATCH {
  NDK_FN_QUERY_EXTENSION_INTERFACE NdkQueryExtension;
  NDK_FN_QUERY_ADAPTER_INFO        NdkQueryAdapterInfo;
  NDK_FN_CREATE_CQ                 NdkCreateCq;
  NDK_FN_CREATE_PD                 NdkCreatePd;
  NDK_FN_CREATE_SHARED_ENDPOINT    NdkCreateSharedEndpoint;
  NDK_FN_CREATE_CONNECTOR          NdkCreateConnector;
  NDK_FN_CREATE_LISTENER           NdkCreateListener;
  NDK_FN_BUILD_LAM                 NdkBuildLAM;
  NDK_FN_RELEASE_LAM               NdkReleaseLAM;
} NDK_ADAPTER_DISPATCH, *PNDK_ADAPTER_DISPATCH;
````


## -struct-fields

### -field NdkQueryExtension

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a> dispatch function.


### -field NdkQueryAdapterInfo

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_query_adapter_info.md">NDK_FN_QUERY_ADAPTER_INFO</a> dispatch function.


### -field NdkCreateCq

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_create_cq.md">NDK_FN_CREATE_CQ</a> dispatch function.


### -field NdkCreatePd

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_create_pd.md">NDK_FN_CREATE_PD</a> dispatch function.


### -field NdkCreateSharedEndpoint

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_create_shared_endpoint.md">NDK_FN_CREATE_SHARED_ENDPOINT</a> dispatch function.


### -field NdkCreateConnector

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_create_connector.md">NDK_FN_CREATE_CONNECTOR</a> dispatch function.


### -field NdkCreateListener

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_create_listener.md">NDK_FN_CREATE_LISTENER</a> dispatch function.


### -field NdkBuildLAM

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_build_lam.md">NDK_FN_BUILD_LAM</a> dispatch function.


### -field NdkReleaseLAM

The entry point for the object's <a href="..\ndkpi\nc-ndkpi-ndk_fn_release_lam.md">NDK_FN_RELEASE_LAM</a> dispatch function.


## -remarks
The <b>NDK_ADAPTER_DISPATCH</b> structure is used in the <a href="netvista.ndk_adapter">NDK_ADAPTER</a> structure.


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
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndk_adapter">NDK_ADAPTER</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_build_lam.md">NDK_FN_BUILD_LAM</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_connector.md">NDK_FN_CREATE_CONNECTOR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_cq.md">NDK_FN_CREATE_CQ</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_listener.md">NDK_FN_CREATE_LISTENER</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_pd.md">NDK_FN_CREATE_PD</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_shared_endpoint.md">NDK_FN_CREATE_SHARED_ENDPOINT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_adapter_info.md">NDK_FN_QUERY_ADAPTER_INFO</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_query_extension_interface.md">NDK_FN_QUERY_EXTENSION_INTERFACE</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_release_lam.md">NDK_FN_RELEASE_LAM</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_ADAPTER_DISPATCH structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

