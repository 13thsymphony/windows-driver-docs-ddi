---
UID: NS.NDKPI._NDK_SHARED_ENDPOINT~R1
title: _NDK_SHARED_ENDPOINT
author: windows-driver-content
description: The NDK_SHARED_ENDPOINT structure specifies the attributes of an NDK shared endpoint object.
old-location: netvista\ndk_shared_endpoint.htm
old-project: NetVista
ms.assetid: 1A6B6EA3-66EE-4736-9457-2A295A7FAF4D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDK_SHARED_ENDPOINT, NDK_SHARED_ENDPOINT
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
req.alt-api: NDK_SHARED_ENDPOINT
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

# _NDK_SHARED_ENDPOINT structure



## -description
The <b>NDK_SHARED_ENDPOINT</b> structure specifies the attributes of an NDK shared endpoint object.



## -syntax

````
typedef struct _NDK_SHARED_ENDPOINT {
  NDK_OBJECT_HEADER                  Header;
  CONST NDK_SHARED_ENDPOINT_DISPATCH *Dispatch;
} NDK_SHARED_ENDPOINT, *PNDK_SHARED_ENDPOINT;
````


## -struct-fields

### -field Header

The <a href="netvista.ndk_object_header">NDK_OBJECT_HEADER</a> structure for the <b>NDK_SHARED_ENDPOINT</b> structure. Set the <b>ObjectType</b> member of the structure that <b>Header</b> specifies to <b>NdkObjectTypeSharedEndpoint</b>.


### -field Dispatch

A pointer to an <a href="netvista.ndk_shared_endpoint_dispatch">NDK_SHARED_ENDPOINT_DISPATCH</a> structure that defines dispatch functions for the NDK shared endpoint object.


## -remarks
NDK provider must set the <b>Dispatch</b> member to its own <a href="netvista.ndk_shared_endpoint_dispatch">NDK_SHARED_ENDPOINT_DISPATCH</a> table before returning a newly created Shared Endpoint object and must NOT use the <b>Dispatch</b> member any more (because the NDK consumer is free to set the <b>Dispatch</b> member to some other value).


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
<a href="netvista.ndk_object_header">NDK_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndk_shared_endpoint_dispatch">NDK_SHARED_ENDPOINT_DISPATCH</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_close_object.md">NDK_FN_CLOSE_OBJECT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_completion.md">NDK_FN_CREATE_COMPLETION</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_create_shared_endpoint.md">NDK_FN_CREATE_SHARED_ENDPOINT</a>
</dt>
<dt>
<a href="netvista.ndkpi_listeners__connectors__and_endpoints">NDKPI Listeners, Connectors, and Endpoints</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDK_SHARED_ENDPOINT structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

