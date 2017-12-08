---
UID: NC.ndis.PROTOCOL_CL_MAKE_CALL_COMPLETE
title: PROTOCOL_CL_MAKE_CALL_COMPLETE
author: windows-driver-content
description: The ProtocolClMakeCallComplete function is used by connection-oriented NDIS clients that make outgoing calls.
old-location: netvista\protocolclmakecallcomplete.htm
old-project: netvista
ms.assetid: 6bb69f78-8dab-46a7-84fb-7bc17e894535
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolClMakeCallComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolClMakeCallComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolClMakeCallComplete
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
---

# PROTOCOL_CL_MAKE_CALL_COMPLETE callback



## -description
The 
  <i>ProtocolClMakeCallComplete</i> function is used by connection-oriented NDIS clients that make outgoing
  calls. Such clients must have 
  <i>ProtocolClMakeCallComplete</i> functions to complete the asynchronous operations that they initiate with 
  <a href="netvista.ndisclmakecall">NdisClMakeCall</a>. Otherwise, such a protocol
  driver's registered 
  <i>ProtocolClMakeCallComplete</i> function can simply return control.


## -prototype

````
PROTOCOL_CL_MAKE_CALL_COMPLETE ProtocolClMakeCallComplete;

VOID ProtocolClMakeCallComplete(
  _In_     NDIS_STATUS         Status,
  _In_     NDIS_HANDLE         ProtocolVcContext,
  _In_opt_ NDIS_HANDLE         NdisPartyHandle,
  _In_     PCO_CALL_PARAMETERS CallParameters
)
{ ... }
````


## -parameters

### -param Status [in]

Specifies the final status of the client's original call to 
     <b>NdisClMakeCall</b>, which can be one of the following:
     


### -param NDIS_STATUS_SUCCESS

The client's attempt to set up a virtual connection succeded. Consequently, the client can
       proceed to make transfers on the active VC using the 
       <i>NdisVcHandle</i> returned by 
       <a href="netvista.ndiscocreatevc">NdisCoCreateVc</a>, which the client has
       stored in its per-VC context area at 
       <i>ProtocolVcContext</i> .

### -param NDIS_STATUS_RESOURCES

NDIS, the call manager, or an underlying driver could not allocate sufficient resources to set
       up the connection.

### -param NDIS_STATUS_XXX

The call manager or underlying miniport driver failed to establish an active connection and NDIS
       propagated this driver-determined failure status to the client.
</dd>
</dl>

### -param ProtocolVcContext [in]

Specifies the handle to the client's per-VC context area, which the client originally supplied to
     NDIS when it called 
     <b>NdisCoCreateVc</b> to set up the VC for its outgoing call.

### -param NdisPartyHandle [in, optional]

If 
     <i>Status</i> is NDIS_STATUS_SUCCESS and the client created a multipoint VC by passing an explicit 
     <i>ProtocolPartyContext</i> handle to 
     <a href="netvista.ndisclmakecall">NdisClMakeCall</a>, this is a valid 
     <i>NdisPartyHandle</i> . Otherwise, this parameter is <b>NULL</b>.
     
<i>ProtocolClMakeCallComplete</i> must save any valid input 
     <i>NdisPartyHandle</i>, usually in the client's per-party context area. The client must use this handle
     if (or when) it makes a subsequent call to 
     <a href="netvista.ndiscldropparty">NdisClDropParty</a> or 
     <a href="netvista.ndisclclosecall">NdisClCloseCall</a> that refers to this
     party.

### -param CallParameters [in]

Pointer to a buffered CO_CALL_PARAMETERS structure. The client allocated this buffer and
     initialized this structure with client-determined data before passing this pointer to 
     <b>NdisClMakeCall</b>. While processing the client's request, the call manager can modify this data to
     reflect the results of its negotiation with the network or with a signaling peer.

## -returns
None

## -remarks
A call to 
    <i>ProtocolClMakeCallComplete</i> indicates that the call manager has completed processing the client's
    request to establish a virtual connection with 
    <b>NdisClMakeCall</b>.

If the client's attempt to establish an outgoing call is unsuccessful (input 
    <i>Status</i> is anything except NDIS_STATUS_SUCCESS), 
    <i>ProtocolClMakeCallComplete</i> should do the following:

Release or prepare for reuse the 
      <i>ProtocolPartyContext</i> area, if any, and the buffer at 
      <i>CallParameters</i> that the client allocated.

Tear down the client-created VC with a call to 
      <a href="netvista.ndiscodeletevc">NdisCoDeleteVc</a> and release or prepare for
      reuse the client-allocated 
      <i>ProtocolVcContext</i> area.

Otherwise, 
    <i>ProtocolClMakeCallComplete</i> should do the following:

Check the 
      <b>Flags</b> member of the structure at 
      <i>CallParameters</i> to see whether CALL_PARAMETERS_CHANGED is set, which indicates that the call
      manager modified the client-supplied call parameters.

If so, examine the data at 
      <i>CallParameters</i> to determine whether they are acceptable for this connection.

For example, the client might retain the buffered call parameters for the active VC, save the 
      <i>NdisPartyHandle</i> if this is a multipoint VC, and generally make the client ready for subsequent
      transfers and other operations on the active VC if it finds the given call parameters satisfactory.

If not, the signaling protocol determines whether the client can attempt to renegotiate for
      acceptable call parameters with the call manager.

For example, a particular call manager might allow its clients to call 
      <a href="netvista.ndisclmodifycallqos">NdisClModifyCallQoS</a> one or more
      times in these circumstances.

If the CM-modified call parameters are unacceptable and further renegotiation is impossible, 
      <i>ProtocolClMakeCallComplete</i> must tear down the call with 
      <a href="netvista.ndisclclosecall">NdisClCloseCall</a>.

In this case, 
      <i>ProtocolClMakeCallComplete</i> should 
      <u>not</u> attempt to release any client-allocated resources on return from 
      <b>NdisClCloseCall</b> but can simply return control. Instead, the client should release the resources
      it allocated (or prepare them for reuse) within its 
      <i>ProtocolClCloseCallComplete</i> function.

To define a <i>ProtocolClMakeCallComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClMakeCallComplete</i> function that is named "MyClMakeCallComplete", use the <b>PROTOCOL_CL_MAKE_CALL_COMPLETE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CL_MAKE_CALL_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_MAKE_CALL_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/97036de6-8b12-4ff1-aae8-f489c4fcde4a">ProtocolClMakeCallComplete
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <i>ProtocolClMakeCallComplete
   (NDIS 5.1)</i>) in Windows XP.
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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndisclclosecall">NdisClCloseCall</a>
</dt>
<dt>
<a href="netvista.ndiscldropparty">NdisClDropParty</a>
</dt>
<dt>
<a href="netvista.ndisclmakecall">NdisClMakeCall</a>
</dt>
<dt>
<a href="netvista.ndiscmmakecallcomplete">NdisCmMakeCallComplete</a>
</dt>
<dt>
<a href="netvista.ndiscocreatevc">NdisCoCreateVc</a>
</dt>
<dt>
<a href="netvista.ndiscodeletevc">NdisCoDeleteVc</a>
</dt>
<dt>
<a href="netvista.ndisfreememory">NdisFreeMemory</a>
</dt>
<dt>
<a href="netvista.ndisfreetonpagedlookasidelist">
   NdisFreeToNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndismcmmakecallcomplete">NdisMCmMakeCallComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_close_call_complete.md">ProtocolClCloseCallComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_make_call.md">ProtocolCmMakeCall</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_MAKE_CALL_COMPLETE callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
