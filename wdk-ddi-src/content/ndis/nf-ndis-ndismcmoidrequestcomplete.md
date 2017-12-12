---
UID: NF.ndis.NdisMCmOidRequestComplete
title: NdisMCmOidRequestComplete macro
author: windows-driver-content
description: The NdisMCmOidRequestComplete function returns the final status of a CoNDIS OID requestthat a miniport call manager (MCM) driver's ProtocolCoOidRequest function previously returned NDIS_STATUS_PENDING for.
old-location: netvista\ndismcmoidrequestcomplete.htm
old-project: netvista
ms.assetid: 4c45be9f-3d07-4150-830a-3aa6d74531ff
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisMCmOidRequestComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCmOidRequestComplete
req.alt-loc: ndis.h
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisMCmOidRequestComplete macro



## -description
The 
  <b>NdisMCmOidRequestComplete</b> function returns the final status of a CoNDIS OID requestthat a miniport
  call manager (MCM) driver's 
  <a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a> function
  previously returned NDIS_STATUS_PENDING for.



## -syntax

````
VOID NdisMCmOidRequestComplete(
  [in]           NDIS_HANDLE       NdisAfHandle,
  [in, optional] NDIS_HANDLE       NdisVcHandle,
  [in, optional] NDIS_HANDLE       NdisPartyHandle,
  [in]           PNDIS_OID_REQUEST OidRequest,
  [in]           NDIS_STATUS       Status
);
````


## -parameters

### -param NdisAfHandle [in]

An address family (AF) handle that NDIS passed to the MCM's 
     <a href="..\ndis\nc-ndis-protocol_co_oid_request.md">
     ProtocolCoOidRequest</a> function.


### -param NdisVcHandle [in, optional]

A virtual connection (VC) handle that NDIS passed to the MCM's 
     <i>ProtocolCoOidRequest</i> function. A <b>NULL</b> value for this parameter indicates that the request is not
     VC-specific. This parameter is <b>NULL</b> if the caller of the 
     <a href="netvista.ndiscooidrequest">NdisCoOidRequest</a> function specified a
     <b>NULL</b> VC handle.


### -param NdisPartyHandle [in, optional]

A party handle that NDIS passed to the MCM's 
     <i>ProtocolCoOidRequest</i> function. A <b>NULL</b> value for this parameter indicates that the request is not
     party-specific. This parameter is <b>NULL</b> if the caller of the 
     <b>NdisCoOidRequest</b> function specified a <b>NULL</b> party handle.


### -param OidRequest [in]

A pointer to an 
     <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structure that the caller
     of the 
     <b>NdisCoOidRequest</b> function supplied.


### -param Status [in]

The final status of the request operation. This parameter can be NDIS_STATUS_SUCCESS,
     NDIS_STATUS_REQUEST_ABORTED, or any driver-determined NDIS_STATUS_<i>XXX</i> status value
     <u>except</u> NDIS_STATUS_PENDING.


## -remarks
A CoNDIS MCM that returns NDIS_STATUS_PENDING from its 
    <a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a> function must
    call the 
    <b>NdisMCmOidRequestComplete</b> function after the MCM has finished the OID request operation.

After the MCM calls 
    <b>NdisMCmOidRequestComplete</b>, NDIS calls the 
    <a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
    ProtocolCoOidRequestComplete</a> function of the CoNDIS client that originally called the 
    <a href="netvista.ndiscooidrequest">NdisCoOidRequest</a> function.

For more information about the OIDs defined to use with CONDIS drivers, see 
    <a href="netvista.ndis_oids">NDIS OIDs</a>.


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
<a href="devtest.ndis_irql_mcm_function">Irql_MCM_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="netvista.ndiscooidrequest">NdisCoOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_oid_request.md">ProtocolCoOidRequest</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_oid_request_complete.md">
   ProtocolCoOidRequestComplete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmOidRequestComplete macro%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

