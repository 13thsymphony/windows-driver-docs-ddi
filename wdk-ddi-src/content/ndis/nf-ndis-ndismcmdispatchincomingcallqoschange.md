---
UID: NF:ndis.NdisMCmDispatchIncomingCallQoSChange
title: NdisMCmDispatchIncomingCallQoSChange macro
author: windows-driver-content
description: NdisMCmDispatchIncomingCallQoSChange notifies a client that a request to change the quality of service on that client's active connection has been received over the network.
old-location: netvista\ndismcmdispatchincomingcallqoschange.htm
old-project: netvista
ms.assetid: e3da62c2-4940-4c55-8232-1780d92b7f1f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NdisMCmDispatchIncomingCallQoSChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisMCmDispatchIncomingCallQoSChange (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers   (see       NdisMCmDispatchIncomingCallQoSChange (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCmDispatchIncomingCallQoSChange
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
req.typenames: *PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE
---

# NdisMCmDispatchIncomingCallQoSChange macro



## -description
<b>NdisMCmDispatchIncomingCallQoSChange</b> notifies a client that a request to change the quality of
  service on that client's active connection has been received over the network.



## -syntax

````
VOID NdisMCmDispatchIncomingCallQoSChange(
  [in] NDIS_HANDLE         NdisVcHandle,
  [in] PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters

### -param NdisVcHandle [in]

Specifies the handle to the VC for which the change in QoS is being requested. The MCM driver
     obtained this handle either when it called 
     <a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a> to set up this connection
     for an incoming call or as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the new
     QoS, requested by the client on the remote node, for this connection.


## -remarks
An MCM driver calls 
    <b>NdisMCmDispatchIncomingCallQoSChange</b> to notify the client that it has received a request to modify
    the QoS on an active connection. Such an MCM driver supports dynamic QoS changes on active calls, which
    is a feature like QoS itself that depends on the signaling protocol.

The MCM driver should call 
    <a href="..\ndis\nf-ndis-ndismcmactivatevc.md">NdisMCmActivateVc</a> whenever it makes
    changes in the call parameters for an active VC.

A call to 
    <b>NdisMCmDispatchIncomingCallQoSChange</b> causes NDIS to call the client's 
    <i>ProtocolClIncomingQoSChange</i> function. The client accepts the proposed modifications to the call
    parameters for the VC by doing nothing, except possibly updating any state it maintains about the QoS for
    the VC, and returning control. Otherwise, the client rejects the proposed QoS change by tearing down the
    call.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDispatchIncomingCallQoSChange</b>. Stand-alone call managers, which register themselves with
    NDIS as protocol drivers, call 
    <b>NdisCmDispatchIncomingCallQoSChange</b> instead.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclmodifycallqos.md">NdisClModifyCallQoS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmdispatchincomingcallqoschange.md">
   NdisCmDispatchIncomingCallQoSChange</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmactivatevc.md">NdisMCmActivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_incoming_call_qos_change.md">
   ProtocolClIncomingCallQosChange</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmDispatchIncomingCallQoSChange macro%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

