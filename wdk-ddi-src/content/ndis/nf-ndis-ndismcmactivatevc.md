---
UID: NF.ndis.NdisMCmActivateVc
title: NdisMCmActivateVc
author: windows-driver-content
description: NdisMCmActivateVc notifies NDIS that an MCM driver is ready to make transfers on a particular VC.
old-location: netvista\ndismcmactivatevc.htm
old-project: netvista
ms.assetid: 2c2e4f7d-578a-4429-baca-ebe45423afff
ms.author: windowsdriverdev
ms.date: 11/30/2017
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
req.iface: 
---

# NdisMCmActivateVc function



## -description
<p><b>NdisMCmActivateVc</b> notifies NDIS that an MCM driver is ready to make transfers on a particular
  VC.</p>


## -syntax

````
NDIS_STATUS NdisMCmActivateVc(
  _In_ NDIS_HANDLE         NdisVcHandle,
  _In_ PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters
<dl>

### -param NdisVcHandle [in]

<dd>
<p>Specifies the handle identifying the VC.</p>
</dd>

### -param CallParameters [in]

<dd>
<p>Pointer to a caller-allocated buffer, formatted as a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>, containing all the
     media-specific parameters that the miniport driver uses for the activated VC.</p>
</dd>
</dl>

## -returns
<p>When 
     <b>NdisMCmActivateVc</b> returns anything other than NDIS_STATUS_PENDING, the MCM driver should make an
     internal call to its 
     <a href="..\ndis\nc-ndis-protocol-cm-activate-vc-complete.md">
     ProtocolCmActivateVcComplete</a> function. Otherwise, NDIS calls the MCM driver's 
     <i>ProtocolCmActivateVcComplete</i> function when this operation is completed.</p>

## -remarks
<p><b>NdisMCmActivateVc</b> informs NDIS that an MCM driver has set up call and media parameters on a newly
    created VC or changed the call parameters on an established VC.</p>

<p>An MCM driver must call 
    <b>NdisMCmActivateVc</b> after establishing a connection on a VC but before any data is sent or received
    on that VC. This call notifies NDIS that the miniport driver has made a NIC ready for transfers on the
    VC.</p>

<p>For a client-initiated outgoing call, an MCM driver usually calls 
    <b>NdisMCmActivateVc</b> following the handshake denoting a negotiated agreement with the remote node or
    successful call-setup at the switch, before it notifies NDIS (and the client) of outgoing call completion
    with 
    <a href="..\ndis\nf-ndis-ndismcmmakecallcomplete.md">NdisMCmMakeCallComplete</a>. For an
    incoming call, an MCM driver usually calls 
    <b>NdisMCmActivateVc</b> after it has called 
    <a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a> successfully and before it
    calls 
    <a href="..\ndis\nf-ndis-ndismcmdispatchincomingcall.md">
    NdisMCmDispatchIncomingCall</a>.</p>

<p>The driver writer determines whether an MCM driver has an (internal) 
    <i>MiniportCoActivateVc</i> function that the driver calls in the context of setting up connections for
    outgoing and incoming calls.</p>

<p>For the duration of the connection, an MCM driver can modify the call parameters as conditions on the
    network change and/or whenever the client calls 
    <a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>. The MCM driver
    must update the state that it maintains about call parameters to the new values if it can continue to
    make transfers on the VC according to the newly modified call parameters. It must call 
    <b>NdisMCmActivateVc</b> to notify NDIS of any changes in the call parameters for the active VC.
    Otherwise, the MCM driver can do either of the following:</p>

<p>Call 
      <b>NdisMCmDeactivateVc</b> after failing the client's request to modify QoS or other call parameters for
      the VC to such a state that the miniport driver cannot continue to make transfers on the VC.</p>

<p>Restore the call parameters to a previously accepted state, notify the client that requested the
      change, and remain ready to continue transferring data on the VC. In this case, the client has the
      option of accepting the restored call parameters or rejecting them and initiating a close of the
      VC.</p>

<p>Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmActivateVc</b>. Stand-alone call managers, which register themselves with NDIS as protocol
    drivers, call 
    <b>NdisCmActivateVc</b> instead.</p>

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
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff552330">NdisMCmActivateVc (NDIS 5.1)</a>) in
   Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisMCmActivateVc (NDIS 5.1)</b>) in
   Windows XP.</p>
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
<a href="..\ndis\nc-ndis-miniport-co-activate-vc.md">MiniportCoActivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmdeactivatevc.md">NdisMCmDeactivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmdispatchincomingcall.md">NdisMCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-co-create-vc.md">ProtocolCoCreateVc</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmActivateVc function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
