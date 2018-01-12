---
UID: NF:ndis.NdisFCancelDirectOidRequest
title: NdisFCancelDirectOidRequest function
author: windows-driver-content
description: Filter drivers call the NdisFCancelDirectOidRequest function to cancel a previous direct OID request to the underlying drivers.
old-location: netvista\ndisfcanceldirectoidrequest.htm
old-project: netvista
ms.assetid: 05cbeca1-7420-41c6-8868-980b265523db
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisFCancelDirectOidRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisFCancelDirectOidRequest
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisFCancelDirectOidRequest function



## -description
Filter drivers call the 
  <b>NdisFCancelDirectOidRequest</b> function to cancel a previous direct OID request to the underlying
  drivers.



## -syntax

````
VOID NdisFCancelDirectOidRequest(
  _In_ NDIS_HANDLE NdisFilterHandle,
  _In_ PVOID       RequestId
);
````


## -parameters

### -param NdisFilterHandle [in]

The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a> function.


### -param RequestId [in]

A cancellation identifier for the request. This identifier specifies the 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## -returns
None


## -remarks
Filter drivers call 
    <b>NdisFCancelDirectOidRequest</b> to cancel a previously issued direct OID request. The request can be
    originated by the filter driver or by overlying drivers. The pointer that is passed at the 
    <i>OidRequest</i> parameter must be the same pointer that was passed in the call to the 
    <a href="..\ndis\nf-ndis-ndisfdirectoidrequest.md">NdisFDirectOidRequest</a> function.

The filter driver can call 
    <b>NdisFCancelDirectOidRequest</b> from the 
    <a href="..\ndis\nc-ndis-filter_cancel_direct_oid_request.md">
    FilterCancelDirectOidRequest</a> function to pass on the cancellation to underlying drivers.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.1 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_cancel_direct_oid_request.md">
   FilterCancelDirectOidRequest</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfdirectoidrequest.md">NdisFDirectOidRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFCancelDirectOidRequest function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

