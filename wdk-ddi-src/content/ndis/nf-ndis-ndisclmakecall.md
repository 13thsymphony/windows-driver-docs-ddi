---
UID: NF.ndis.NdisClMakeCall
title: NdisClMakeCall function
author: windows-driver-content
description: NdisClMakeCall sets up an outgoing call on a client-created VC.
old-location: netvista\ndisclmakecall.htm
old-project: netvista
ms.assetid: 69775220-71d8-497c-aaf7-9bc3ec90d00f
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisClMakeCall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClMakeCall (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClMakeCall (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisClMakeCall
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
---

# NdisClMakeCall function



## -description
<b>NdisClMakeCall</b> sets up an outgoing call on a client-created VC.



## -syntax

````
NDIS_STATUS NdisClMakeCall(
  _In_      NDIS_HANDLE         NdisVcHandle,
  _Inout_   PCO_CALL_PARAMETERS CallParameters,
  _In_opt_  NDIS_HANDLE         ProtocolPartyContext,
  _Out_opt_ PNDIS_HANDLE        NdisPartyHandle
);
````


## -parameters

### -param NdisVcHandle [in]

Specifies the handle returned by a preceding call to 
     <a href="netvista.ndiscocreatevc">NdisCoCreateVc</a>.


### -param CallParameters [in, out]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> in which the caller has
     specified the attributes for this connection, such as the address of the target for the call, latency,
     bandwidth, and quality of service if the network medium and address family supported by the call manager
     permits QoS specifications.


### -param ProtocolPartyContext [in, optional]

Optionally specifies a caller-supplied handle to a resident context area in which the client will
     maintain per-party state for the initial party on its multipoint VC. This parameter is <b>NULL</b> if the given
     VC does not represent a multipoint connection. For a multipoint VC, NDIS passes this handle back to the
     client's ProtocolCl<i>Xxx</i> functions in all subsequent calls that affect this particular party.


### -param NdisPartyHandle [out, optional]

Pointer to a caller-supplied variable, usually in the caller-allocated party context area, in
     which NDIS returns a handle representing the initial party to the multipoint connection if the request
     to set up an outgoing call is successful. If 
     <i>ProtocolPartyContext</i> is <b>NULL</b>, this variable, usually in the client's VC context area, also is set
     to <b>NULL</b> on completion of outgoing-call setup.


## -returns
When 
     <b>NdisClMakeCall</b> returns anything other than NDIS_STATUS_PENDING, the client should make an internal
     call to its 
     <a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">
     ProtocolClMakeCallComplete</a> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClMakeCallComplete</i> function when this operation is completed.


## -remarks
<b>NdisClMakeCall</b> sets up the attributes of a client-created VC for a client-initiated outgoing call.
    The client must set up the VC with 
    <a href="netvista.ndiscocreatevc">NdisCoCreateVc</a> before it attempts to make
    an outgoing call.

A call to 
    <b>NdisClMakeCall</b> causes NDIS to forward this request to the 
    <a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a> function of the
    call manager with which the client shares the given 
    <a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">NdisVcHandle</a>. The CM is
    responsible for validating the given data at 
    <i>CallParameters</i> . It can modify this client-supplied data while negotiating with relevant network
    components and can return different traffic parameters than the client originally gave to 
    <b>NdisClMakeCall</b>. The client's 
    <i>
    ProtocolClMakeCallComplete</i> function is responsible for accepting the modified call parameters if
    this occurs or for tearing down the call if the CM's proposed call parameters are unacceptable.

Consequently, the data at 
    <i>CallParameters</i> must remain available to the call manager at least for the duration of call setup.
    The client cannot free this buffer when 
    <b>NdisClMakeCall</b> returns NDIS_STATUS_PENDING. It must defer releasing this client-allocated resource
    until its 
    <i>ProtocolClMakeCallComplete</i> function is called.

If 
    <b>NdisClMakeCall</b> sets up a multipoint connection, the client is establishing the traffic parameters
    globally for the given VC, unless the underlying network medium supports per-party traffic
    parameters.

The client's 
    <i>ProtocolClMakeCallComplete</i> function should check the input 
    <i>Status</i> for NDIS_STATUS_SUCCESS before it uses any returned handle at 
    <i>NdisPartyHandle</i> . If the call manager fails the request to set up a call on a multipoint
    connection, the value of this client-supplied variable is invalid.


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
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff550884">NdisClMakeCall (NDIS 5.1)</a>) in
   Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisClMakeCall (NDIS 5.1)</b>) in
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
<a href="devtest.ndis_irql_protocol_driver_function">Irql_Protocol_Driver_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndiscladdparty">NdisClAddParty</a>
</dt>
<dt>
<a href="netvista.ndisclclosecall">NdisClCloseCall</a>
</dt>
<dt>
<a href="netvista.ndisclmodifycallqos">NdisClModifyCallQoS</a>
</dt>
<dt>
<a href="netvista.ndiscmactivatevc">NdisCmActivateVc</a>
</dt>
<dt>
<a href="netvista.ndiscmmakecallcomplete">NdisCmMakeCallComplete</a>
</dt>
<dt>
<a href="netvista.ndiscocreatevc">NdisCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_make_call_complete.md">ProtocolClMakeCallComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisClMakeCall function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

