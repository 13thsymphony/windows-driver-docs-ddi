---
UID: NF:ndis.NdisCmDispatchIncomingCall
title: NdisCmDispatchIncomingCall function
author: windows-driver-content
description: NdisCmDispatchIncomingCall informs the client of an incoming call on a SAP previously registered by that client.
old-location: netvista\ndiscmdispatchincomingcall.htm
old-project: netvista
ms.assetid: 2172aeec-8502-414e-9d01-9292c0eb7ce8
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisCmDispatchIncomingCall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmDispatchIncomingCall   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmDispatchIncomingCall   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCmDispatchIncomingCall
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
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCmDispatchIncomingCall function



## -description
<b>NdisCmDispatchIncomingCall</b> informs the client of an incoming call on a SAP previously registered by
  that client.



## -syntax

````
NDIS_STATUS NdisCmDispatchIncomingCall(
  _In_ NDIS_HANDLE         NdisSapHandle,
  _In_ NDIS_HANDLE         NdisVcHandle,
  _In_ PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters

### -param NdisSapHandle [in]

Specifies the handle identifying the SAP. NDIS set up this handle when the client originally
     called 
     <a href="..\ndis\nf-ndis-ndisclregistersap.md">NdisClRegisterSap</a>, and the call
     manager originally obtained this handle as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">
     ProtocolCmRegisterSap</a> function.


### -param NdisVcHandle [in]

Specifies the handle identifying the VC, created with 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a> when the call manager
     processes the incoming call offer directed to this registered SAP.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the
     traffic and media parameters for the VC.


## -returns
When 
     <b>NdisCmDispatchIncomingCall</b> returns anything other than NDIS_STATUS_PENDING, the call manager
     should make an internal call to its 
     <a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
     ProtocolCmIncomingCallComplete</a> function. Otherwise, NDIS calls the CM's 
     <i>ProtocolCmIncomingCallComplete</i> function when this operation is completed.


## -remarks
Before calling 
    <b>NdisCmDispatchIncomingCall</b>, a stand-alone call manager has already done the following:

Identified the target SAP, previously registered by a particular client, for the call (actually, a
      request to make a connection) that it received over the network

Created a VC for the incoming call with 
      <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>


Possibly negotiated about acceptable call parameters over the network, or accepted the call
      parameters sent from the remote node

Activated the VC with 
      <a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>, causing the
      underlying miniport driver to make itself ready for transfers on the VC in accord with the negotiated
      or accepted call parameters

The CM's call to 
    <b>NdisCmDispatchIncomingCall</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a> function,
    within which the client either accepts or rejects the requested connection. After deciding whether to
    accept the connection, the client calls 
    <a href="..\ndis\nf-ndis-ndisclincomingcallcomplete.md">NdisClIncomingCallComplete</a>,
    which, in turn, calls the CM's 
    <a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
    ProtocolCmIncomingCallComplete</a> function. If the client accepted the call, the CM next calls 
    <a href="..\ndis\nf-ndis-ndiscmdispatchcallconnected.md">NdisCmDispatchCallConnected</a>.
    Otherwise, it deactivates (and possibly deletes) the VC it created, after notifying the remote node that
    the offered call was rejected.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDispatchIncomingCall</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmDispatchIncomingCall</b> instead.


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
   <a href="https://msdn.microsoft.com/21b9228f-1a65-422b-8706-a6976219a6dd">NdisCmDispatchIncomingCall
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisCmDispatchIncomingCall
   (NDIS 5.1)</b>) in Windows XP.

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
<a href="..\ndis\nf-ndis-ndisclregistersap.md">NdisClRegisterSap</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclincomingcallcomplete.md">NdisClIncomingCallComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmdispatchcallconnected.md">NdisCmDispatchCallConnected</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscosendnetbufferlists.md">NdisCoSendNetBufferLists</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmdispatchincomingcall.md">NdisMCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
   ProtocolCmIncomingCallComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_receive_net_buffer_lists.md">
   ProtocolCoReceiveNetBufferLists</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmDispatchIncomingCall function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

