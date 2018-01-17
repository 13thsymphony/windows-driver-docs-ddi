---
UID: NC:ndis.PROTOCOL_CL_ADD_PARTY_COMPLETE
title: PROTOCOL_CL_ADD_PARTY_COMPLETE function
author: windows-driver-content
description: The ProtocolClAddPartyComplete function is required for connection-oriented NDIS clients that set up multipoint connections.
old-location: netvista\protocolcladdpartycomplete.htm
old-project: netvista
ms.assetid: ea3ebbe9-fd94-44b8-8801-639d099c5158
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PROTOCOL_CL_ADD_PARTY_COMPLETE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolClAddPartyComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolClAddPartyComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolClAddPartyComplete
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
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# PROTOCOL_CL_ADD_PARTY_COMPLETE function



## -description
The 
  <i>ProtocolClAddPartyComplete</i> function is required for connection-oriented NDIS clients that set up
  multipoint connections. Such clients must have 
  <i>ProtocolClAddPartyComplete</i> functions to complete the asynchronous operations that they initiate with 
  <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>. Otherwise, such a protocol
  driver's registered 
  <i>ProtocolClAddPartyComplete</i> function can simply return control.



## -syntax

````
PROTOCOL_CL_ADD_PARTY_COMPLETE ProtocolClAddPartyComplete;

VOID ProtocolClAddPartyComplete(
  _In_ NDIS_STATUS         Status,
  _In_ NDIS_HANDLE         ProtocolPartyContext,
  _In_ NDIS_HANDLE         NdisPartyHandle,
  _In_ PCO_CALL_PARAMETERS CallParameters
)
{ ... }
````


## -parameters

### -param Status [in]

Specifies final status of the client-initiated add-party operation, which can be one of the
     following:
     




### -param NDIS_STATUS_SUCCESS

The given party was added on the client's active multipoint VC.


### -param NDIS_STATUS_RESOURCES

NDIS could not allocate sufficient resources to track the new party.


### -param NDIS_STATUS_FAILURE

The client passed an invalid 
       <i>NdisVcHandle</i> to 
       <b>NdisClAddParty</b>.


### -param NDIS_STATUS_XXX

The call manager's 
       <a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a> function
       returned a CM-determined value to indicate why it could not add the party to the VC.

</dd>
</dl>

### -param ProtocolPartyContext [in]

Specifies the client-supplied handle originally passed to 
     <b>NdisClAddParty</b>.


### -param NdisPartyHandle [in]

If 
     <i>Status</i> is NDIS_STATUS_SUCCESS, this NDIS-supplied handle represents the association between the
     call manager and client regarding this party. Otherwise, the attempt to add a party failed and the
     client should consider this parameter an invalid handle.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>, originally set up by
     the client for its call to 
     <b>NdisClAddParty</b> but possibly modified subsequently by the call manager.


## -returns
None


## -remarks
A call to 
    <i>ProtocolClAddPartyComplete</i> indicates completion of the asynchronous operation initiated when the
    client called 
    <a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>. If the input 
    <i>Status</i> is set to anything other than NDIS_STATUS_SUCCESS, 
    <i>ProtocolClAddPartyComplete</i> can release or reuse the client-allocated buffers at 
    <i>ProtocolPartyContext</i> and at 
    <i>CallParameters</i> .

If the attempt to add a party succeeded, 
    <i>ProtocolClAddPartyComplete</i> should save the input 
    <i>NdisPartyHandle</i> for subsequent calls to NDIS library functions concerning this party in the
    client's 
    <i>ProtocolPartyContext</i> area. For example, the client must pass this handle in a subsequent call to 
    <a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a> eventually unless the
    remote party that it represents closes its connection first.

The structure at 
    <i>CallParameters</i> originally was allocated and initialized by the client, which passed this pointer to
    
    <b>NdisClAddParty</b>. However, the call manager might have modified the client-supplied values to
    reflect the results of the CM's negotiation with the network or with a signaling peer while processing
    the client's add-party request. To determine whether the call manager made any modifications, 
    <i>ProtocolClAddPartyComplete</i> can check the 
    <b>Flags</b> member of this structure for whether CALL_PARAMETERS_CHANGED is set. If so, 
    <i>ProtocolClAddPartyComplete</i> must update the per-party state that the client maintains for this call
    at 
    <i>ProtocolPartyContext</i> unless it finds the CM's modifications unacceptable. The particular signaling
    protocol determines what the client can do in this case. Usually, a client calls 
    <b>NdisClDropParty</b> if it finds the CM-modified call parameters unacceptable.

Depending on the signaling protocol of the call manager, the traffic parameters at 
    <i>CallParameters</i> can be identical for all parties on any particular multipoint connection. That is,
    as the client of such a call manager adds parties on a multipoint connection that the client originally
    set up with 
    <a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>, it can supply only the
    target address of each party and leave the traffic parameters as originally set up for the multipoint VC
    each time it calls 
    <b>NdisClAddParty</b>.

To define a <i>ProtocolClAddPartyComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClAddPartyComplete</i> function that is named "MyClAddPartyComplete", use the <b>PROTOCOL_CL_ADD_PARTY_COMPLETE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CL_ADD_PARTY_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_ADD_PARTY_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscladdparty.md">NdisClAddParty</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclmakecall.md">NdisClMakeCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmaddpartycomplete.md">NdisCmAddPartyComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmaddpartycomplete.md">NdisMCmAddPartyComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_incoming_drop_party.md">ProtocolClIncomingDropParty</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_add_party.md">ProtocolCmAddParty</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_ADD_PARTY_COMPLETE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

