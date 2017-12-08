---
UID: NF.ndis.NdisMCmActivateVc
title: NdisMCmActivateVc function
author: windows-driver-content
description: NdisMCmActivateVc notifies NDIS that an MCM driver is ready to make transfers on a particular VC.
old-location: netvista\ndismcmactivatevc.htm
old-project: netvista
ms.assetid: 2c2e4f7d-578a-4429-baca-ebe45423afff
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisMCmActivateVc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmActivateVc (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmActivateVc (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCmActivateVc
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_MCM_Function
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

# NdisMCmActivateVc function



## -description
<b>NdisMCmActivateVc</b> notifies NDIS that an MCM driver is ready to make transfers on a particular
  VC.


## -syntax

````
NDIS_STATUS NdisMCmActivateVc(
  _In_ NDIS_HANDLE         NdisVcHandle,
  _In_ PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters

### -param NdisVcHandle [in]

Specifies the handle identifying the VC.

### -param CallParameters [in]

Pointer to a caller-allocated buffer, formatted as a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>, containing all the
     media-specific parameters that the miniport driver uses for the activated VC.

## -returns
When 
     <b>NdisMCmActivateVc</b> returns anything other than NDIS_STATUS_PENDING, the MCM driver should make an
     internal call to its 
     <a href="..\ndis\nc-ndis-protocol_cm_activate_vc_complete.md">
     ProtocolCmActivateVcComplete</a> function. Otherwise, NDIS calls the MCM driver's 
     <i>ProtocolCmActivateVcComplete</i> function when this operation is completed.

## -remarks
<b>NdisMCmActivateVc</b> informs NDIS that an MCM driver has set up call and media parameters on a newly
    created VC or changed the call parameters on an established VC.

An MCM driver must call 
    <b>NdisMCmActivateVc</b> after establishing a connection on a VC but before any data is sent or received
    on that VC. This call notifies NDIS that the miniport driver has made a NIC ready for transfers on the
    VC.

For a client-initiated outgoing call, an MCM driver usually calls 
    <b>NdisMCmActivateVc</b> following the handshake denoting a negotiated agreement with the remote node or
    successful call-setup at the switch, before it notifies NDIS (and the client) of outgoing call completion
    with 
    <a href="netvista.ndismcmmakecallcomplete">NdisMCmMakeCallComplete</a>. For an
    incoming call, an MCM driver usually calls 
    <b>NdisMCmActivateVc</b> after it has called 
    <a href="netvista.ndismcmcreatevc">NdisMCmCreateVc</a> successfully and before it
    calls 
    <a href="netvista.ndismcmdispatchincomingcall">
    NdisMCmDispatchIncomingCall</a>.

The driver writer determines whether an MCM driver has an (internal) 
    <i>MiniportCoActivateVc</i> function that the driver calls in the context of setting up connections for
    outgoing and incoming calls.

For the duration of the connection, an MCM driver can modify the call parameters as conditions on the
    network change and/or whenever the client calls 
    <a href="netvista.ndisclmodifycallqos">NdisClModifyCallQoS</a>. The MCM driver
    must update the state that it maintains about call parameters to the new values if it can continue to
    make transfers on the VC according to the newly modified call parameters. It must call 
    <b>NdisMCmActivateVc</b> to notify NDIS of any changes in the call parameters for the active VC.
    Otherwise, the MCM driver can do either of the following:

Call 
      <b>NdisMCmDeactivateVc</b> after failing the client's request to modify QoS or other call parameters for
      the VC to such a state that the miniport driver cannot continue to make transfers on the VC.

Restore the call parameters to a previously accepted state, notify the client that requested the
      change, and remain ready to continue transferring data on the VC. In this case, the client has the
      option of accepting the restored call parameters or rejecting them and initiating a close of the
      VC.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmActivateVc</b>. Stand-alone call managers, which register themselves with NDIS as protocol
    drivers, call 
    <b>NdisCmActivateVc</b> instead.

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
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff552330">NdisMCmActivateVc (NDIS 5.1)</a>) in
   Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisMCmActivateVc (NDIS 5.1)</b>) in
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
<a href="devtest.ndis_irql_mcm_function">Irql_MCM_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">MiniportCoActivateVc</a>
</dt>
<dt>
<a href="netvista.ndisclmakecall">NdisClMakeCall</a>
</dt>
<dt>
<a href="netvista.ndisclmodifycallqos">NdisClModifyCallQoS</a>
</dt>
<dt>
<a href="netvista.ndiscmactivatevc">NdisCmActivateVc</a>
</dt>
<dt>
<a href="netvista.ndismcmdeactivatevc">NdisMCmDeactivateVc</a>
</dt>
<dt>
<a href="netvista.ndismcmdispatchincomingcall">NdisMCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="netvista.ndismcmcreatevc">NdisMCmCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmActivateVc function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
