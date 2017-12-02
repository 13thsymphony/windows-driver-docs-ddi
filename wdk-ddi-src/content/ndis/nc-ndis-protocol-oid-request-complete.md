---
UID: NC.ndis.PROTOCOL_OID_REQUEST_COMPLETE
title: PROTOCOL_OID_REQUEST_COMPLETE
author: windows-driver-content
description: The ProtocolOidRequestComplete function completes the processing of a protocol driver-initiated OID request for which the NdisOidRequest function returned NDIS_STATUS_PENDING.Note  You must declare the function by using the PROTOCOL_OID_REQUEST_COMPLETE type. For more information, see the following Examples section.
old-location: netvista\protocoloidrequestcomplete.htm
old-project: netvista
ms.assetid: 2706577e-ba03-4347-9672-7303752ec0fe
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolOidRequestComplete
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# PROTOCOL_OID_REQUEST_COMPLETE callback



## -description
<p>The 
  <i>ProtocolOidRequestComplete</i> function completes the processing of a protocol
  driver-initiated OID request for which the 
  <a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a> function returned
  NDIS_STATUS_PENDING.</p>


## -prototype

````
PROTOCOL_OID_REQUEST_COMPLETE ProtocolOidRequestComplete;

VOID ProtocolOidRequestComplete(
  _In_ NDIS_HANDLE       ProtocolBindingContext,
  _In_ PNDIS_OID_REQUEST OidRequest,
  _In_ NDIS_STATUS       Status
)
{ ... }
````


## -parameters
<dl>

### -param ProtocolBindingContext [in]

<dd>
<p>A handle to a protocol driver-allocated context area in which the protocol driver maintains
     per-binding run-time state. The driver supplied this handle when it called the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.</p>
</dd>

### -param OidRequest [in]

<dd>
<p>A pointer to the protocol driver-supplied 
     <a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a> structure that was
     previously passed to the 
     <b>NdisOidRequest</b> function.</p>
</dd>

### -param Status [in]

<dd>
<p>The final status of the request. The underlying driver or NDIS determines this final status. This
     parameter determines what 
     <i>ProtocolOidRequestComplete</i> does with the information at 
     <i>OidRequest</i>.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><i>ProtocolOidRequestComplete</i> uses the input value of 
    <i>Status</i> as follows:</p>

<p>If 
      <i>Status</i> is NDIS_STATUS_SUCCESS, the 
      <b>BytesRead</b> or 
      <b>BytesWritten</b> member of the 
      <a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a> structure has been set
      by NDIS or the underlying driver to specify how much protocol driver-supplied information was
      transferred from the buffer at 
      <b>InformationBuffer</b> to the NIC in a set operation or how much information
      was returned at 
      <b>InformationBuffer</b> in response to a query operation.</p>

<p>If the protocol driver made a query, 
      <i>ProtocolOidRequestComplete</i> can use the data returned at 
      <b>InformationBuffer</b> in any way determined by the protocol driver, depending
      on the value of the 
      <b>Oid</b> member.</p>

<p>For example, if the protocol driver originally initiated an 
      <a href="netvista.oid_gen_maximum_send_packets">
      OID_GEN_MAXIMUM_SEND_PACKETS</a> query, 
      <i>ProtocolOidRequestComplete</i> might set up state variables in the 
      <i>ProtocolBindingContext</i> area to throttle the number of outstanding sends the
      driver will set up for subsequent calls to the 
      <b>NdisSendNetBufferLIsts</b> function.</p>

<p>If 
      <i>Status</i> is NDIS_STATUS_INVALID_LENGTH or NDIS_STATUS_BUFFER_TOO_SHORT, the 
      <b>BytesNeeded</b> member specifies the OID-specific value of the 
      <b>InformationBufferLength</b> member required to carry out the requested
      operation.</p>

<p>In these circumstances, 
      <i>ProtocolOidRequestComplete</i> can allocate sufficient buffer space for the
      request, set up another NDIS_OID_REQUEST structure with the required 
      <b>InformationBufferLength</b> and same 
      <b>Oid</b>, and retry the call to the 
      <a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a> function.</p>

<p><i>ProtocolOidRequestComplete</i> can retry requests for certain other NDIS_STATUS_
      <i>XXX</i> arguments, as well, as described in the reference for the 
      <a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a> function.</p>

<p>If 
      <i>Status</i> is an NDIS_STATUS_
      <i>XXX</i> value that is an unrecoverable error, 
      <i>ProtocolOidRequestComplete</i> should release the memory allocated for the
      NDIS_OID_REQUEST structure and determine whether the driver should close the binding, or adjust its
      binding-specific state information to handle continued network I/O operations on the binding.</p>

<p>For global queries and sets, the underlying connectionless miniport driver's call to the 
    <a href="..\ndis\nf-ndis-ndismoidrequestcomplete.md">NdisMOidRequestComplete</a> function
    causes NDIS to call the 
    <i>ProtocolOidRequestComplete</i> function. NDIS forwards the miniport
    driver-determined 
    <i>Status</i> passed to 
    <b>NdisMOidRequestComplete</b> as the input 
    <i>Status</i> to 
    <i>ProtocolOidRequestComplete</i>.</p>

<p>For binding-specific queries, NDIS calls the 
    <i>ProtocolOidRequestComplete</i> function itself. Because the NDIS library maintains
    bindings for all miniport drivers, NDIS can return binding-specific information only about underlying
    drivers that report their medium-type as one for which the system provides a filter library. NDIS returns
    NDIS_STATUS_NOT_SUPPORTED for protocol driver-initiated binding-specific queries to other miniport
    drivers.</p>

<p>For more information about system-defined OIDs, see 
    <a href="netvista.ndis_oids">NDIS OIDs</a>.</p>

<p><i>ProtocolOidRequestComplete</i> can be called before the protocol driver has had
    time to inspect the status code that 
    <b>NdisOidRequest</b> returns at 
    <i>Status</i>.</p>

<p>NDIS calls 
    <i>ProtocolOidRequestComplete</i> at IRQL &lt;= DISPATCH_LEVEL.</p>

<p>To define a <i>ProtocolOidRequestComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ProtocolOidRequestComplete</i> function that is named "MyOidRequestComplete", use the <b>PROTOCOL_OID_REQUEST_COMPLETE</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>PROTOCOL_OID_REQUEST_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_OID_REQUEST_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
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
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismoidrequestcomplete.md">NdisMOidRequestComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisoidrequest.md">NdisOidRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569600">OID_GEN_MAXIMUM_SEND_PACKETS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_OID_REQUEST_COMPLETE callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
