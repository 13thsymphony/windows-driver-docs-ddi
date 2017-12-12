---
UID: NF.ndis.NdisSynchronousOidRequest
title: NdisSynchronousOidRequest function
author: windows-driver-content
description: Protocol drivers call the NdisSynchronousOidRequest function to originate a new Synchronous OID request and issue it to underlying drivers.
old-location: netvista\ndissynchronousoidrequest.htm
old-project: netvista
ms.assetid: BF539DDA-59ED-4010-88BC-3C7D8DC475EF
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisSynchronousOidRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisSynchronousOidRequest
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
---

# NdisSynchronousOidRequest function



## -description
Protocol drivers call the <b>NdisSynchronousOidRequest</b> function to originate a new Synchronous OID request and issue it to underlying drivers.



## -syntax

````
NDIS_STATUS NdisSynchronousOidRequest(
  _In_ NDIS_HANDLE      NdisBindingHandle,
  _In_ NDIS_OID_REQUEST *OidRequest
);
````


## -parameters

### -param NdisBindingHandle [in]

The handle returned by the <a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a> function that identifies the target miniport adapter on the binding.


### -param OidRequest [in]

A pointer to an 
     <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structure that specifies
     the operation that is requested with a given OID_<i>Xxx</i> code. The structure can specify an OID query, set, or method request.


## -returns
The underlying driver determines which NDIS_STATUS_<i>XXX</i> code 
     <b>NdisSynchronousOidRequest</b> returns, but it is usually one of the following values:
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>The request operation completed successfully.
<dl>
<dt><b>NDIS_STATUS_INVALID_OID</b></dt>
</dl>The OID_<i>Xxx</i> code that was specified in the 
       <b>Oid</b> member of the 
       <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a>-structured buffer at 
       <i>OidRequest</i> was invalid or unsupported by the underlying driver.
<dl>
<dt><b>NDIS_STATUS_INVALID_LENGTH or NDIS_STATUS_BUFFER_TOO_SHORT</b></dt>
</dl>The value that was specified in the 
       <b>InformationBufferLength</b> member of the NDIS_OID_REQUEST-structured buffer at 
       <i>OidRequest</i> did not match the requirements for the given OID_<i>Xxx</i> code. If the information buffer was too small, the 
       <b>BytesNeeded</b> member contains the correct value for 
       <b>InformationBufferLength</b> on return from 
       <b>NdisSynchronousOidRequest</b>.
<dl>
<dt><b>NDIS_STATUS_INVALID_DATA</b></dt>
</dl>The data that was supplied at 
       <b>InformationBuffer</b> in the given NDIS_OID_REQUEST structure was invalid for the given OID_<i>Xxx</i> code.
<dl>
<dt><b>NDIS_STATUS_NOT_SUPPORTED or NDIS_STATUS_NOT_RECOGNIZED</b></dt>
</dl>The underlying driver does not support the requested operation.
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>The request could not be satisfied because of a resource shortage. Typically, this return value
       indicates that an attempt to allocate memory was unsuccessful, but it does not necessarily indicate
       that the same request, submitted later, will be failed for the same reason.
<dl>
<dt><b>NDIS_STATUS_NOT_ACCEPTED</b></dt>
</dl>The underlying driver attempted the requested operation, typically a set on a NIC, but it
       failed. For example, an attempt to set too many multicast addresses might cause the return of this
       value.
<dl>
<dt><b>NDIS_STATUS_CLOSING or NDIS_STATUS_CLOSING_INDICATING</b></dt>
</dl>The underlying driver failed the requested operation because a close operation is in
       progress.
<dl>
<dt><b>NDIS_STATUS_RESET_IN_PROGRESS</b></dt>
</dl>The underlying miniport driver cannot satisfy the request at this time because it is currently
       resetting the affected NIC. The caller's 
       <a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a> function was or
       will be called with NDIS_STATUS_RESET_START to indicate that a reset is in progress. This return value
       does not necessarily indicate that the same request, submitted later, will be failed for the same
       reason.
<dl>
<dt><b>NDIS_STATUS_FAILURE</b></dt>
</dl>This value typically is a non-specific default, returned when none of the more specific
       NDIS_STATUS_<i>Xxx</i> values caused the underlying driver to fail the request.

 


## -remarks
The <b>NdisSynchronousOidRequest</b> function cannot be used for general OID requests. For general OID requests, use the <a href="netvista.ndisoidrequest">NdisOidRequest</a> function instead. <b>NdisSynchronousOidRequest</b> can be used only for OIDs that NDIS supports for use with the Synchronous OID interface. Most protocol drivers do not need to call <b>NdisSynchronousOidRequest</b>

Protocol drivers must not close the adapter binding until any Synchronous OID requests originated by the protocol driver are completed.


Protocol drivers are not required to implement <a href="..\ndis\nc-ndis-protocol_oid_request_complete.md">ProtocolOidRequestComplete</a> or <a href="..\ndis\nc-ndis-protocol_direct_oid_request_complete.md">ProtocolDirectOidRequestComplete</a> in order to call <b>NdisSynchronousOidRequest</b>. As its name suggests, a Synchronous OID request always completes synchronously, so there is no asynchronous callback.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows 10, version 1709

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
<a href="netvista.ndisopenadapterex">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="netvista.ndisoidrequest">NdisOidRequest</a>
</dt>
<dt>
<a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_oid_request_complete.md">ProtocolOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_direct_oid_request_complete.md">ProtocolDirectOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisSynchronousOidRequest function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

