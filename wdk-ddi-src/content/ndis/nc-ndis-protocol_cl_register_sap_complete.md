---
UID: NC.ndis.PROTOCOL_CL_REGISTER_SAP_COMPLETE
title: PROTOCOL_CL_REGISTER_SAP_COMPLETE
author: windows-driver-content
description: A connection-oriented NDIS client that accepts incoming calls must have a ProtocolClRegisterSapComplete function to complete the asynchronous operations that it initiates with NdisClRegisterSap.
old-location: netvista\protocolclregistersapcomplete.htm
old-project: NetVista
ms.assetid: b0a2a224-3353-4f20-b14f-ed5d633a6ead
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClRegisterSapComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClRegisterSapComplete (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolClRegisterSapComplete
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

# PROTOCOL_CL_REGISTER_SAP_COMPLETE callback



## -description
A connection-oriented NDIS client that accepts incoming calls must have 
  a <i>ProtocolClRegisterSapComplete</i> function to complete the asynchronous operations that it initiates
  with 
  <a href="netvista.ndisclregistersap">NdisClRegisterSap</a>. Otherwise, such a
  protocol driver's registered 
  <i>ProtocolClRegisterSapComplete</i> function can simply return control.



## -prototype

````
PROTOCOL_CL_REGISTER_SAP_COMPLETE ProtocolClRegisterSapComplete;

VOID ProtocolClRegisterSapComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE ProtocolSapContext,
  _In_ PCO_SAP     Sap,
  _In_ NDIS_HANDLE NdisSapHandle
)
{ ... }
````


## -parameters

### -param Status [in]

Specifies the final status of the client's call to 
     <b>NdisClRegisterSap</b>, which can be one of the following:
     




### -param NDIS_STATUS_SUCCESS

The SAP has been registered both with NDIS and the call manager, which will subsequently call 
       <a href="netvista.ndiscmdispatchincomingcall">
       NdisCmDispatchIncomingCall</a> whenever it receives an incoming call offer directed to the given
       SAP, thereby causing NDIS to call the client's 
       <a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">
       ProtocolClIncomingCall</a> function.


### -param NDIS_STATUS_RESOURCES

NDIS or the call manager could not allocate and/or initialize necessary resources to register
       and maintain the SAP.


### -param NDIS_STATUS_INVALID_DATA

The client supplied an invalid specification at 
       <i>Sap</i> to NDIS, which it forwarded to the call manager's 
       <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a> function
       for validation.


### -param NDIS_STATUS_XXX

The call manager encountered an error in attempting to register the given SAP and NDIS
       propagated this CM-determined failure status to the client.

</dd>
</dl>

### -param ProtocolSapContext [in]

Specifies the handle to the client's per-SAP context area, which the client originally supplied to
     NDIS when it called 
     <a href="netvista.ndisclregistersap">NdisClRegisterSap</a>. If the registration
     is successful, NDIS retains this context handle and uses it subsequently in calls to the client's 
     <i>ProtocolClIncomingCall</i> function pertaining to this SAP.


### -param Sap [in]

Pointer to the client-allocated buffer containing the specification for the SAP to be opened. The
     client originally passed this pointer to 
     <b>NdisClRegisterSap</b>.


### -param NdisSapHandle [in]

If 
     <i>Status</i> is NDIS_STATUS_SUCCESS, specifies an NDIS-supplied valid handle to this registered SAP,
     effectively an association established with NDIS between the client and a particular call manager for
     the client-specified SAP. Otherwise, this parameter is <b>NULL</b>. The client must save a valid handle,
     preferably in its 
     <i>ProtocolSapContext</i> area, for an eventual call to 
     <a href="netvista.ndisclderegistersap">NdisClDeregisterSap</a>.


## -returns
None


## -remarks
NDIS calls 
    <i>ProtocolClRegisterSapComplete</i> to indicate that the client's previous call to 
    <b>NdisClRegisterSap</b> has been processed by NDIS and, if NDIS did not fail the call, by the call
    manager with which the client shares the 
    <i>NdisAfHandle</i> that it passed to 
    <b>NdisClRegisterSap</b>.

To receive incoming calls through a connection-oriented NIC, a client's 
    <a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">
    ProtocolCoAfRegisterNotify</a> or 
    <a href="..\ndis\nc-ndis-protocol_cl_open_af_complete_ex.md">
    ProtocolClOpenAfCompleteEx</a> function usually registers one or more SAPs with the call manager.

To register each SAP, the client calls 
    <b>NdisClRegisterSap</b>, passing in the 
    <i>NdisAfHandle</i> that identifies the call manager from which the client wants to receive notifications
    of incoming calls, and NDIS returns the client an 
    <i>NdisSapHandle</i> to the registered SAP if the client's call to 
    <b>NdisClRegisterSap</b> succeeds. 
    <i>ProtocolClRegisterSapComplete</i> must save each valid 
    <i>NdisSapHandle</i>, usually in the client's per-SAP 
    <i>ProtocolSapContext</i> area so it can release the SAP later with 
    <a href="netvista.ndisclderegistersap">NdisClDeregisterSap</a>.

The format of a SAP is specific to the call manager. If the call manager does not recognize the SAP
    that the client is attempting to register or if the specified SAP is already in use, the call manager can
    fail the SAP registration. 
    <i>ProtocolClRegisterSapComplete</i> should check the input 
    <i>Status</i> for NDIS_STATUS_SUCCESS before proceding further. If the attempt to register the SAP failed,
    
    <i>ProtocolClRegisterSapComplete</i> can either release the per-SAP context area and buffer at 
    <i>Sap</i> that the client allocated or prepare them for reuse in another call to 
    <b>NdisClRegisterSap</b>.

A client can receive incoming calls on a SAP even while SAP registration is still pending, that is,
    before its 
    <i>ProtocolClRegisterSapComplete</i> function is called.

To define a <i>ProtocolClRegisterSapComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClRegisterSapComplete</i> function that is named "MyClRegisterSapComplete", use the <b>PROTOCOL_CL_REGISTER_SAP_COMPLETE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CL_REGISTER_SAP_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_REGISTER_SAP_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/e3455864-a948-40d1-a180-aa1a00f157a2">
   ProtocolClRegisterSapComplete (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <i>
   ProtocolClRegisterSapComplete (NDIS 5.1)</i>) in Windows XP.

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
<a href="netvista.ndisclderegistersap">NdisClDeregisterSap</a>
</dt>
<dt>
<a href="netvista.ndisclregistersap">NdisClRegisterSap</a>
</dt>
<dt>
<a href="netvista.ndiscmdispatchincomingcall">NdisCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="netvista.ndiscmregistersapcomplete">NdisCmRegisterSapComplete</a>
</dt>
<dt>
<a href="netvista.ndisfreememory">NdisFreeMemory</a>
</dt>
<dt>
<a href="netvista.ndisfreetonpagedlookasidelist">
   NdisFreeToNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndismcmdispatchincomingcall">NdisMCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="netvista.ndismcmregistersapcomplete">NdisMCmRegisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_open_af_complete_ex.md">ProtocolClOpenAfCompleteEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_af_register_notify.md">ProtocolCoAfRegisterNotify</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20PROTOCOL_CL_REGISTER_SAP_COMPLETE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

