---
UID: NE.ndkpi._NDK_OBJECT_TYPE
title: _NDK_OBJECT_TYPE
author: windows-driver-content
description: The NDK_OBJECT_TYPE enumeration defines types of Network Direct Kernel (NDK) objects.
old-location: netvista\ndk_object_type.htm
old-project: netvista
ms.assetid: 8CB39DF6-00DA-4480-A44E-62CAF1DB35CE
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDK_OBJECT_TYPE, NDK_OBJECT_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDK_OBJECT_TYPE
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

# _NDK_OBJECT_TYPE enumeration



## -description
The <b>NDK_OBJECT_TYPE</b> enumeration defines  types of Network Direct Kernel (NDK) objects.



## -syntax

````
typedef enum _NDK_OBJECT_TYPE { 
  NdkObjectTypeUndefined       = 0,
  NdkObjectTypeAdapter         = 1,
  NdkObjectTypeQp              = 2,
  NdkObjectTypeCq              = 3,
  NdkObjectTypeMr              = 4,
  NdkObjectTypeMw              = 5,
  NdkObjectTypePd              = 6,
  NdkObjectTypeSharedEndpoint  = 7,
  NdkObjectTypeConnector       = 8,
  NdkObjectTypeListener        = 9,
  NdkObjectTypeSrq             = 10,
  NdkObjectTypeMax             = 11
} NDK_OBJECT_TYPE;
````


## -enum-fields

### -field NdkObjectTypeUndefined

Specifies  an undefined NDK  object.


### -field NdkObjectTypeAdapter

Specifies an NDK adapter object (<a href="netvista.ndk_adapter">NDK_ADAPTER</a>).


### -field NdkObjectTypeQp

Specifies an NDK queue pair (QP) object (<a href="netvista.ndk_qp">NDK_QP</a>).


### -field NdkObjectTypeCq

Specifies an NDK completion queue (CQ) object (<a href="netvista.ndk_cq">NDK_CQ</a>).


### -field NdkObjectTypeMr

Specifies an NDK memory region (MR) object (<a href="netvista.ndk_mr">NDK_MR</a>).


### -field NdkObjectTypeMw

Specifies an NDK memory window (MW) object (<a href="netvista.ndk_mw">NDK_MW</a>).


### -field NdkObjectTypePd

Specifies an NDK protection domain (PD) object (<a href="netvista.ndk_pd">NDK_PD</a>).


### -field NdkObjectTypeSharedEndpoint

Specifies an NDK shared endpoint object (<a href="netvista.ndk_shared_endpoint">NDK_SHARED_ENDPOINT</a>).


### -field NdkObjectTypeConnector

Specifies an NDK connector object (<a href="netvista.ndk_connector">NDK_CONNECTOR</a>).


### -field NdkObjectTypeListener

Specifies an NDK listener object (<a href="netvista.ndk_listener">NDK_LISTENER</a>).


### -field NdkObjectTypeSrq

Specifies an NDK shared receive queue (SRQ) object (<a href="netvista.ndk_srq">NDK_SRQ</a>).


### -field NdkObjectTypeMax

The maximum value for this enumeration. This value might change in future versions of the header files and binaries. 




## -remarks
NDK objects include an <a href="netvista.ndk_object_header">NDK_OBJECT_HEADER</a> structure that packages the object type,  version, and other information.


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
<a href="netvista.ndk_connector">NDK_CONNECTOR</a>
</dt>
<dt>
<a href="netvista.ndk_cq">NDK_CQ</a>
</dt>
<dt>
<a href="netvista.ndk_listener">NDK_LISTENER</a>
</dt>
<dt>
<a href="netvista.ndk_mr">NDK_MR</a>
</dt>
<dt>
<a href="netvista.ndk_mw">NDK_MW</a>
</dt>
<dt>
<a href="netvista.ndk_object_header">NDK_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndk_pd">NDK_PD</a>
</dt>
<dt>
<a href="netvista.ndk_qp">NDK_QP</a>
</dt>
<dt>
<a href="netvista.ndk_shared_endpoint">NDK_SHARED_ENDPOINT</a>
</dt>
<dt>
<a href="netvista.ndk_srq">NDK_SRQ</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_OBJECT_TYPE enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

