---
UID: NF.ndis.NdisFCancelOidRequest
title: NdisFCancelOidRequest function
author: windows-driver-content
description: Filter drivers call the NdisFCancelOidRequest function to cancel a previous request to the underlying drivers.
old-location: netvista\ndisfcanceloidrequest.htm
old-project: netvista
ms.assetid: 67dc0769-0d65-4048-84aa-1100883bde46
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisFCancelOidRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisFCancelOidRequest
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_OID_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisFCancelOidRequest function



## -description
Filter drivers call the 
  <b>NdisFCancelOidRequest</b> function to cancel a previous request to the underlying drivers.



## -syntax

````
VOID NdisFCancelOidRequest(
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
     <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## -returns
None


## -remarks
Filter drivers call 
    <b>NdisFCancelOidRequest</b> to cancel a previously issued request. The request can be originated by the
    filter driver or by overlying drivers. The pointer passed at 
    <i>OidRequest</i> must be the same pointer that was passed in the call to the 
    <a href="netvista.ndisfoidrequest">NdisFOidRequest</a> function.

The filter driver can call 
    <b>NdisFCancelOidRequest</b> from the 
    <a href="..\ndis\nc-ndis-filter_cancel_oid_request.md">FilterCancelOidRequest</a> function
    to pass on the cancellation to underlying drivers.


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
Supported in NDIS 6.0 and later.

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
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.ndis_irql_oid_function">Irql_OID_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-filter_attach.md">FilterAttach</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-filter_cancel_oid_request.md">FilterCancelOidRequest</a>
</dt>
<dt>
<a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="netvista.ndisfoidrequest">NdisFOidRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisFCancelOidRequest function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

