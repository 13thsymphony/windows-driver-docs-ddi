---
UID: NF.ndis.NdisCancelOidRequest
title: NdisCancelOidRequest
author: windows-driver-content
description: Protocol drivers call the NdisCancelOidRequest function to cancel a previous request to the underlying drivers.
old-location: netvista\ndiscanceloidrequest.htm
old-project: netvista
ms.assetid: 4cb12ac3-7cb6-4773-b680-d77a55b19246
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NdisCancelOidRequest
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
req.alt-api: NdisCancelOidRequest
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
req.iface: 
---

# NdisCancelOidRequest function



## -description
<p>Protocol drivers call the 
  <b>NdisCancelOidRequest</b> function to cancel a previous request to the underlying drivers.</p>


## -syntax

````
VOID NdisCancelOidRequest(
  _In_ NDIS_HANDLE NdisBindingHandle,
  _In_ PVOID       RequestId
);
````


## -parameters
<dl>

### -param <i>NdisBindingHandle</i> [in]

<dd>
<p>The handle returned by the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function that
     identifies the target adapter on the binding.</p>
</dd>

### -param <i>RequestId</i> [in]

<dd>
<p>A cancellation identifier for the request. This identifier specifies the 
     <a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a> structures that are being
     canceled.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>Protocol drivers call this function to cancel a previously issued request. The request ID that is
    passed at the 
    <i>RequestId</i> parameter must match the request ID in the 
    <a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a> structure that was passed
    in the call to the 
    <a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a> function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.ndis_irql_oid_function">Irql_OID_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCancelOidRequest function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
