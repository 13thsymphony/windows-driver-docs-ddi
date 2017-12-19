---
UID: NF.ndis.NdisMCmDispatchIncomingCall
title: NdisMCmDispatchIncomingCall macro
author: windows-driver-content
description: NdisMCmDispatchIncomingCall informs the client of an incoming call on a SAP previously registered by that client with the MCM driver.
old-location: netvista\ndismcmdispatchincomingcall.htm
old-project: NetVista
ms.assetid: 24102e1f-375e-4bf4-8a43-6527b90c8564
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: NdisMCmDispatchIncomingCall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDispatchIncomingCall   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDispatchIncomingCall   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCmDispatchIncomingCall
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
---

# NdisMCmDispatchIncomingCall macro



## -description
<b>NdisMCmDispatchIncomingCall</b> informs the client of an incoming call on a SAP previously registered by
  that client with the MCM driver.



## -syntax

````
NDIS_STATUS NdisMCmDispatchIncomingCall(
  [in] NDIS_HANDLE         NdisSapHandle,
  [in] NDIS_HANDLE         NdisVcHandle,
  [in] PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters

### -param NdisSapHandle [in]

Specifies the handle identifying the SAP. NDIS set up this handle when the client originally
     called 
     <a href="netvista.ndisclregistersap">NdisClRegisterSap</a>, and the MCM driver
     obtained this handle as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">
     ProtocolCmRegisterSap</a> function.


### -param NdisVcHandle [in]

Specifies the handle identifying the VC, created with 
     <a href="netvista.ndismcmcreatevc">NdisMCmCreateVc</a> when the MCM driver
     processes the incoming call offer directed to this registered SAP.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> that specifies the call
     and media parameters for the VC.


## -remarks
Before calling 
    <b>NdisMCmDispatchIncomingCall</b>, an MCM driver has already done the following:

Identified the target SAP, previously registered by a particular client, for the call (actually, a
      request to make a connection) that it received over the network

Created a VC for the incoming call with 
      <a href="netvista.ndismcmcreatevc">NdisMCmCreateVc</a>


Possibly negotiated about acceptable call parameters over the network, or accepted the call
      parameters sent from the remote node

Activated the VC with 
      <a href="netvista.ndismcmactivatevc">NdisMCmActivateVc</a> to notify NDIS that
      it is ready for transfers on the VC in accord with the negotiated or accepted call parameters

The MCM driver's call to 
    <b>NdisMCmDispatchIncomingCall</b> causes NDIS to call the client's 
    <i>ProtocolClIncomingCall</i> function, within which the client either accepts or rejects the requested
    connection. After deciding whether to accept the connection, the client calls 
    <a href="netvista.ndisclincomingcallcomplete">NdisClIncomingCallComplete</a>,
    which, in turn, calls the MCM driver's 
    <i>ProtocolCmIncomingCallComplete</i> function. If the client accepted the call, the MCM driver next calls
    
    <a href="netvista.ndismcmdispatchcallconnected">
    NdisMCmDispatchCallConnected</a>. Otherwise, it deactivates (and possibly deletes) the VC it created,
    after notifying the remote node that the offered call was rejected.

Only connection-oriented miniport drivers that provide integrated call-management support call 
    <b>NdisMCmDispatchIncomingCall</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDispatchIncomingCall</b> instead.


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
   <a href="https://msdn.microsoft.com/f6eec685-4923-4040-82e7-03ffad5c1263">NdisMCmDispatchIncomingCall
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisMCmDispatchIncomingCall
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
<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>
</dt>
<dt>
<a href="netvista.ndisclregistersap">NdisClRegisterSap</a>
</dt>
<dt>
<a href="netvista.ndisclincomingcallcomplete">NdisClIncomingCallComplete</a>
</dt>
<dt>
<a href="netvista.ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="netvista.ndismcmactivatevc">NdisMCmActivateVc</a>
</dt>
<dt>
<a href="netvista.ndismcmcreatevc">NdisMCmCreateVc</a>
</dt>
<dt>
<a href="netvista.ndismcmdeactivatevc">NdisMCmDeactivateVc</a>
</dt>
<dt>
<a href="netvista.ndismcmdispatchcallconnected">NdisMCmDispatchCallConnected</a>
</dt>
<dt>
<a href="netvista.ndismcmdeletevc">NdisMCmDeleteVc</a>
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
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NdisMCmDispatchIncomingCall macro%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

