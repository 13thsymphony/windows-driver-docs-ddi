---
UID: NF:ndis.NdisClRegisterSap
title: NdisClRegisterSap function
author: windows-driver-content
description: NdisClRegisterSap registers a SAP on which the client can receive incoming calls from a remote node.
old-location: netvista\ndisclregistersap.htm
old-project: netvista
ms.assetid: 33ed0839-d1e3-4872-baa8-ead7e97f8c53
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisClRegisterSap
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClRegisterSap (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClRegisterSap (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisClRegisterSap
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Protocol_Driver_Function
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

# NdisClRegisterSap function



## -description
<b>NdisClRegisterSap</b> registers a SAP on which the client can receive incoming calls from a remote
  node.



## -syntax

````
NDIS_STATUS NdisClRegisterSap(
  _In_  NDIS_HANDLE  NdisAfHandle,
  _In_  NDIS_HANDLE  ProtocolSapContext,
  _In_  PCO_SAP      Sap,
  _Out_ PNDIS_HANDLE NdisSapHandle
);
````


## -parameters

### -param NdisAfHandle [in]

Specifies the handle returned by 
     <a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">NdisClOpenAddressFamilyEx</a>,
     which implicitly identifies the call manager with which to register the SAP.


### -param ProtocolSapContext [in]

Specifies the handle to a caller-supplied resident context area in which the client maintains
     state for this SAP after it has been opened. NDIS passes this handle back to the client in all
     subsequent calls concerning this SAP if the call to 
     <b>NdisClRegisterSap</b> succeeds.


### -param Sap [in]

Pointer to a client-supplied specification for the SAP to be opened, formatted as a structure of
     type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545392">CO_SAP</a>.


### -param NdisSapHandle [out]

Pointer to a variable in which a handle to the newly registered SAP is returned if this call
     succeeds.


## -returns
When 
     <b>NdisClRegisterSap</b> returns anything other than NDIS_STATUS_PENDING, the client should make an
     internal call to its 
     <a href="..\ndis\nc-ndis-protocol_cl_register_sap_complete.md">
     ProtocolClRegisterSapComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClRegisterSapComplete</i> function when this operation is completed.


## -remarks
With a call to 
    <b>NdisClRegisterSap</b>, a client requests notifications of incoming calls on a particular SAP. NDIS
    forwards the given SAP information to the call manager's 
    <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a> function
    for validation. If the given SAP is already in use or if the call manager does not recognize the
    client-supplied specification at 
    <i>Sap</i>, the call manager fails this request.

SAP format is medium-dependent and specific to the address family supported by the call manager, which
    uses registered SAPs subsequently to route incoming calls to the appropriate client. A call manager can
    register SAPs for established PVCs without contacting other network components, depending on the
    underlying medium.

If its call to 
    <b>NdisClRegisterSap</b> succeeds, the client must save the handle returned at 
    <i>NdisSapHandle</i> because it is a required parameter to 
    <a href="..\ndis\nf-ndis-ndisclderegistersap.md">NdisClDeregisterSap</a>. Callers of 
    <b>NdisClRegisterSap</b> usually pass a pointer to a variable in the client-allocated state area at 
    <i>ProtocolSapContext</i> so that NDIS can set it to the 
    <i>NdisSapHandle</i> if this call succeeds. NDIS passes the given 
    <i>ProtocolSapContext</i> to the client's registered ProtocolCl/Co<i>Xxx</i> functions in all subsequent calls concerning this SAP until the client calls 
    <b>NdisClDeregisterSap</b>.

Usually, a client calls 
    <b>NdisClRegisterSap</b> from its 
    <i>ProtocolAfRegisterNotify</i> function following its successful call to 
    <a href="..\ndis\nf-ndis-ndisclopenaddressfamilyex.md">NdisClOpenAddressFamilyEx</a>.
    Registering one or more SAPs allows the client to receive its incoming call(s) as soon as the call
    manager receives them over the network.

By contrast with client-initiated outgoing calls, a client does not call 
    <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> before it calls 
    <b>NdisClRegisterSap</b>. For incoming calls, the call manager initiates the creation of the VC, as
    follows:

On receipt of an incoming call on a registered SAP, the call manager first calls 
      <b>NdisCoCreateVc</b>, causing NDIS to call the client's 
      <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.

When the VC has been set up and activated, the call manager calls 
      <a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>,
      causing NDIS to call the client's 
      <a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">
      ProtocolClIncomingCall</a> function.


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
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff550916">NdisClRegisterSap (NDIS 5.1)</a>) in
   Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisClRegisterSap (NDIS 5.1)</b>) in
   Windows XP.

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547996">Irql_Protocol_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545392">CO_SAP</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclderegistersap.md">NdisClDeregisterSap</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_register_sap_complete.md">
   ProtocolClRegisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">ProtocolCoAfRegisterNotify</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisClRegisterSap function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

