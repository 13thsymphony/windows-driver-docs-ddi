---
UID: NF.ndis.NdisCmActivateVc
title: NdisCmActivateVc
author: windows-driver-content
description: NdisCmActivateVc passes CM-supplied call parameters, including media parameters, for a particular VC down to the underlying miniport driver.
old-location: netvista\ndiscmactivatevc.htm
old-project: netvista
ms.assetid: 9091426c-3174-4367-b7c7-5684877efe9c
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NdisCmActivateVc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmActivateVc (NDIS 5.1)) in   Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmActivateVc (NDIS 5.1)) in   Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCmActivateVc
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_CallManager_Function
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

# NdisCmActivateVc function



## -description
<p><b>NdisCmActivateVc</b> passes CM-supplied call parameters, including media parameters, for a particular VC
  down to the underlying miniport driver.</p>


## -syntax

````
NDIS_STATUS NdisCmActivateVc(
  _In_    NDIS_HANDLE         NdisVcHandle,
  _Inout_ PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters
<dl>

### -param <i>NdisVcHandle</i> [in]

<dd>
<p>Specifies the handle identifying the VC on which to set call parameters. The call manager either
     obtained this handle from 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> for an incoming call or as
     an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol-co-create-vc.md">ProtocolCoCreateVc</a> function for a
     client-initiated outgoing call.</p>
</dd>

### -param <i>CallParameters</i> [in, out]

<dd>
<p>Pointer to a CM-allocated resident buffer, formatted as a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>, containing all the
     media-specific parameters that the underlying miniport driver uses for VC activation.</p>
</dd>
</dl>

## -returns
<p>When 
     <b>NdisCmActivateVc</b> returns anything other than NDIS_STATUS_PENDING, the call manager should make an
     internal call to its 
     <a href="..\ndis\nc-ndis-protocol-cm-activate-vc-complete.md">
     ProtocolCmActivateVcComplete</a> function. Otherwise, NDIS calls the CM's 
     <i>ProtocolCmActivateVcComplete</i> function when this operation is completed.</p>

## -remarks
<p><b>NdisCmActivateVc</b> notifies the underlying miniport driver to set up call and media parameters on a
    newly created VC or to change those of an established VC. NDIS forwards the given call parameters and VC
    handle to the underlying miniport driver's 
    <a href="..\ndis\nc-ndis-miniport-co-activate-vc.md">MiniportCoActivateVc</a> function, which
    sets up all necessary resources to track the state of the VC and makes itself and a NIC ready for data
    transfers on the VC.</p>

<p>A stand-alone CM always calls 
    <b>NdisCmActivateVc</b> after establishing a connection on a VC but before any data is sent or received on
    that VC. For the duration of the connection, a CM can call 
    <b>NdisCmActivateVc</b> many times with the same 
    <i>NdisVcHandle</i> as conditions on the network change and/or whenever the client calls 
    <a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>. At each such
    call to 
    <b>NdisCmActivateVc</b>, the underlying miniport driver's 
    <i>MiniportCoActivateVc</i> function must do either of the following:</p>

<p>Update the state that the miniport driver maintains about call parameters to the new values supplied
      by the call manager if the miniport driver can continue to make transfers on the VC according to the
      newly modified call parameters.</p>

<p>Fail the call if the miniport driver cannot continue to make transfers under the constraints of the
      given call parameters.</p>

<p>When the underlying miniport driver fails a request to set or reset call parameters, the call manager
    might modify its original specification at 
    <i>CallParameters</i> and call 
    <b>NdisCmActivateVc</b> again. The limit on the number of times any call manager makes repeated attempts
    to activate a VC is implementation-dependent.</p>

<p>For a client-initiated outgoing call, a stand-alone CM usually calls 
    <b>NdisCmActivateVc</b> immediately following the packet exchange confirming a negotiated agreement with
    the remote target of the call or successful call-setup at the switch, before it notifies NDIS (and the
    client) of outgoing call completion with 
    <a href="..\ndis\nf-ndis-ndiscmmakecallcomplete.md">NdisCmMakeCallComplete</a>. For an
    incoming call, a call manager usually calls 
    <b>NdisCmActivateVc</b> after it has called 
    <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> successfully and before it
    calls 
    <a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">
    NdisCmDispatchIncomingCall</a>.</p>

<p>In the process of setting up an outgoing call and while any VC remains activated, the client can
    request changes to the call parameters for that VC, for example, by calling 
    <a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQos</a>. After verifying
    the validity of the given call parameters for any such a request, the stand-alone call manager must call 
    <b>NdisCmActivateVc</b> to pass the modified call parameters down to the underlying miniport driver.</p>

<p>Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmActivateVc</b>. Connection-oriented miniport drivers that provide integrated call-management
    support call 
    <b>NdisMCmActivateVc</b> instead.</p>

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
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff550919">NdisCmActivateVc (NDIS 5.1)</a>) in
   Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisCmActivateVc (NDIS 5.1)</b>) in
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
<a href="devtest.ndis_irql_callmanager_function">Irql_CallManager_Function</a>
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
<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQos</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmdispatchincomingcall.md">NdisCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmactivatevc.md">NdisMCmActivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-cm-activate-vc-complete.md">
   ProtocolCmActivateVcComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-co-create-vc.md">ProtocolCoCreateVc</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmActivateVc function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
