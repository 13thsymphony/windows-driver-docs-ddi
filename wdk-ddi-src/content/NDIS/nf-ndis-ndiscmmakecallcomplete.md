---
UID: NF.ndis.NdisCmMakeCallComplete
title: NdisCmMakeCallComplete
author: windows-driver-content
description: NdisCmMakeCallComplete returns the final status of a client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to make an outgoing call.
old-location: netvista\ndiscmmakecallcomplete.htm
ms.assetid: e2c1f849-daf0-479c-9f1d-906149ac550e
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: netvista
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   NdisCmMakeCallComplete (NDIS
   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   NdisCmMakeCallComplete (NDIS
   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCmMakeCallComplete
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
ms.keywords: NdisCmMakeCallComplete
req.iface: 
---

# NdisCmMakeCallComplete function



## -description
<p><b>NdisCmMakeCallComplete</b> returns the final status of a client's request, for which the call manager
  previously returned NDIS_STATUS_PENDING, to make an outgoing call.</p>


## -syntax

````
VOID NdisCmMakeCallComplete(
  _In_     NDIS_STATUS         Status,
  _In_     NDIS_HANDLE         NdisVcHandle,
  _In_opt_ NDIS_HANDLE         NdisPartyHandle,
  _In_opt_ NDIS_HANDLE         CallMgrPartyContext,
  _In_     PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters
<dl>

### -param <i>Status</i> [in]

<dd>
<p>Specifies the final status of the attempt to make the connection, either NDIS_STATUS_SUCCESS or
     any CM-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.</p>
</dd>

### -param <i>NdisVcHandle</i> [in]

<dd>
<p>Specifies the handle to the client-created VC, which the call manager originally obtained as an
     input parameter to its 
     <a href="https://msdn.microsoft.com/b086dd24-74f5-474a-8684-09bf92ac731b">ProtocolCoCreateVc</a> function. More
     recently, the CM obtained this handle from its per-VC state designated by the 
     <i>CallMgrVcContext</i> passed in to its 
     <a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a> function.</p>
</dd>

### -param <i>NdisPartyHandle</i> [in, optional]

<dd>
<p>Specifies the handle to the initial party on the client-created multipoint VC, which the call
     manager obtained as an input parameter to its 
     <i>ProtocolCmMakeCall</i> function. If the given 
     <i>NdisVcHandle</i> represented a point-to-point VC, this parameter was <b>NULL</b>.</p>
</dd>

### -param <i>CallMgrPartyContext</i> [in, optional]

<dd>
<p>Specifies the CM-supplied handle to a caller-allocated resident context area, in which the CM will
     maintain per-party state information, or <b>NULL</b> if 
     <i>NdisPartyHandle</i> is <b>NULL</b>. For a multipoint VC, NDIS passes this CM-supplied 
     <i>CallManagerPartyContext</i> handle in all subsequent calls to the ProtocolCm<i>Xxx</i> functions that concern this party. Otherwise, NDIS ignores this parameter.</p>
</dd>

### -param <i>CallParameters</i> [in]

<dd>
<p>Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the call
     parameters set up for this connection if 
     <i>Status</i> is NDIS_STATUS_SUCCESS.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>A stand-alone call manager should call 
    <b>NdisMCmMakeCallComplete</b> with NDIS_STATUS_SUCCESS only if the underlying miniport driver is ready to
    make data transfers on the VC. That is, the call manager has negotiated with the network to establish
    call parameters for the VC and called 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561649">NdisCmActivateVc</a> successfully.</p>

<p>A stand-alone call manager must call 
    <b>NdisCmMakeCallComplete</b> if its 
    <a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a> function
    previously returned NDIS_STATUS_PENDING for the given 
    <i>NdisVcHandle</i> . The client that initiated the pending outgoing call cannot use the VC to make
    transfers until the CM calls 
    <b>NdisCmMakeCallComplete</b> with NDIS_STATUS_SUCCESS.</p>

<p>Even if the attempted connection failed, neither NDIS nor the client can release the resources they
    allocated to maintain state until the CM's call to 
    <b>NdisCmMakeCallComplete</b> causes a call to that client's 
    <a href="https://msdn.microsoft.com/6bb69f78-8dab-46a7-84fb-7bc17e894535">
    ProtocolClMakeCallComplete</a> function. In fact, neglecting to call 
    <b>NdisCmMakeCallComplete</b> for a failed attempt to set up such a connection causes a memory leak in the
    call manager as well; it prevents the client from tearing down the VC it created for its failed outgoing
    call, so the CM is not called to release the resources it allocated for that VC.</p>

<p>If the CM passes an error, such as NDIS_STATUS_FAILURE, for the 
    <i>Status</i>, it should consider the 
    <i>NdisPartyHandle</i>, if any, invalid as soon as it calls 
    <b>NdisCmMakeCallComplete</b>. The CM can release (or reinitialize for reuse) any resources that it
    allocated to maintain state for the given party when 
    <b>NdisCmMakeCallComplete</b> returns control. The CM's 
    <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function will
    subsequently be called to release any resources that the CM allocated for tracking the state of the
    client-created VC whenever the CM passes an error status to 
    <b>NdisCmMakeCallComplete</b>.</p>

<p>In the course of setting up a client-initiated outgoing call, the CM can modify the client-supplied
    call parameters originally passed in to its 
    <a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a> function. If it
    does, the CM must pass its modifications in the buffer at 
    <i>CallParameters</i> when it calls 
    <b>NdisCmMakeCallComplete</b>. If the client finds these modified call parameters unacceptable, it will
    then tear down the call, which also causes a call to the CM's 
    <i>ProtocolCoDeleteVc</i> function.</p>

<p>Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmMakeCallComplete</b>. Miniport drivers that provide integrated call-management support call 
    <a href="https://msdn.microsoft.com/b518f36e-5937-4a74-a1d4-9e1709750843">
    NdisMCmMakeCallComplete</a> instead.</p>

<p>A stand-alone call manager should call 
    <b>NdisMCmMakeCallComplete</b> with NDIS_STATUS_SUCCESS only if the underlying miniport driver is ready to
    make data transfers on the VC. That is, the call manager has negotiated with the network to establish
    call parameters for the VC and called 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561649">NdisCmActivateVc</a> successfully.</p>

<p>A stand-alone call manager must call 
    <b>NdisCmMakeCallComplete</b> if its 
    <a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a> function
    previously returned NDIS_STATUS_PENDING for the given 
    <i>NdisVcHandle</i> . The client that initiated the pending outgoing call cannot use the VC to make
    transfers until the CM calls 
    <b>NdisCmMakeCallComplete</b> with NDIS_STATUS_SUCCESS.</p>

<p>Even if the attempted connection failed, neither NDIS nor the client can release the resources they
    allocated to maintain state until the CM's call to 
    <b>NdisCmMakeCallComplete</b> causes a call to that client's 
    <a href="https://msdn.microsoft.com/6bb69f78-8dab-46a7-84fb-7bc17e894535">
    ProtocolClMakeCallComplete</a> function. In fact, neglecting to call 
    <b>NdisCmMakeCallComplete</b> for a failed attempt to set up such a connection causes a memory leak in the
    call manager as well; it prevents the client from tearing down the VC it created for its failed outgoing
    call, so the CM is not called to release the resources it allocated for that VC.</p>

<p>If the CM passes an error, such as NDIS_STATUS_FAILURE, for the 
    <i>Status</i>, it should consider the 
    <i>NdisPartyHandle</i>, if any, invalid as soon as it calls 
    <b>NdisCmMakeCallComplete</b>. The CM can release (or reinitialize for reuse) any resources that it
    allocated to maintain state for the given party when 
    <b>NdisCmMakeCallComplete</b> returns control. The CM's 
    <a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a> function will
    subsequently be called to release any resources that the CM allocated for tracking the state of the
    client-created VC whenever the CM passes an error status to 
    <b>NdisCmMakeCallComplete</b>.</p>

<p>In the course of setting up a client-initiated outgoing call, the CM can modify the client-supplied
    call parameters originally passed in to its 
    <a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a> function. If it
    does, the CM must pass its modifications in the buffer at 
    <i>CallParameters</i> when it calls 
    <b>NdisCmMakeCallComplete</b>. If the client finds these modified call parameters unacceptable, it will
    then tear down the call, which also causes a call to the CM's 
    <i>ProtocolCoDeleteVc</i> function.</p>

<p>Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmMakeCallComplete</b>. Miniport drivers that provide integrated call-management support call 
    <a href="https://msdn.microsoft.com/b518f36e-5937-4a74-a1d4-9e1709750843">
    NdisMCmMakeCallComplete</a> instead.</p>

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
   <a href="https://msdn.microsoft.com/299ad109-0c17-4a6d-8629-a4f6ad9b0436">NdisCmMakeCallComplete (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisCmMakeCallComplete (NDIS
   5.1)</b>) in Windows XP.</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547917">Irql_CallManager_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/df690a05-359d-44f0-b063-4fc21d6c4d76">
   NdisAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561635">NdisClMakeCall</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563544">NdisMCmMakeCallComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/6bb69f78-8dab-46a7-84fb-7bc17e894535">ProtocolClMakeCallComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/ede0a18a-cd3b-4fbb-a16b-e7493940d633">ProtocolCmMakeCall</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/d761270f-bf77-441e-834c-9ac7fb3d350f">ProtocolCoDeleteVc</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmMakeCallComplete function%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
