---
UID: NC.ndis.PROTOCOL_CL_DROP_PARTY_COMPLETE
title: PROTOCOL_CL_DROP_PARTY_COMPLETE
author: windows-driver-content
description: The ProtocolClDropPartyComplete function is used by connection-oriented NDIS clients that set up multipoint connections.
old-location: netvista\protocolcldroppartycomplete.htm
old-project: netvista
ms.assetid: c916f379-393c-41d7-ab30-2f3181c3ada6
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClDropPartyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClDropPartyComplete (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolClDropPartyComplete
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

# PROTOCOL_CL_DROP_PARTY_COMPLETE callback



## -description
The 
  <i>ProtocolClDropPartyComplete</i> function is used by connection-oriented NDIS clients that set up
  multipoint connections. Such clients must have 
  <i>ProtocolClDropPartyComplete</i> functions to complete the asynchronous operations that they initiate with
  
  <a href="netvista.ndiscldropparty">NdisClDropParty</a>. Otherwise, such a protocol
  driver's registered 
  <i>ProtocolClDropPartyComplete</i> function can simply return control.


## -prototype

````
PROTOCOL_CL_DROP_PARTY_COMPLETE ProtocolClDropPartyComplete;

VOID ProtocolClDropPartyComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE ProtocolPartyContext
)
{ ... }
````


## -parameters

### -param Status [in]

Specifies the final status of the client-initiated drop-party operation, which can be one of the
     following:
     


### -param NDIS_STATUS_SUCCESS

The party has been dropped. The 
       <i>NdisPartyHandle</i> that represented this party, which the client stored in its 
       <i>ProtocolPartyContext</i> area, is now invalid.

### -param NDIS_STATUS_FAILURE

The given party was the last remaining on the client's multipoint VC. Therefore, the client
       should call 
       <a href="netvista.ndisclclosecall">NdisClCloseCall</a> to drop this
       party.
</dd>
</dl>

### -param ProtocolPartyContext [in]

Specifies the handle to the client's per-party context area, which the client originally supplied
     to NDIS either when it called 
     <a href="netvista.ndiscladdparty">NdisClAddParty</a> or 
     <a href="netvista.ndisclmakecall">NdisClMakeCall</a>.

## -returns
None

## -remarks
A call to 
    <i>ProtocolClDropPartyComplete</i> indicates that the call manager has completed processing of the request
    initiated by the client's previous call to 
    <a href="netvista.ndiscldropparty">NdisClDropParty</a>. 
    <i>ProtocolClDropPartyComplete</i> can either release the client-allocated per-party context area or
    prepare it for reuse in a subsequent call to 
    <b>NdisClAddParty</b>.

If the client is in the process of tearing down a multipoint VC that it created, 
    <i>ProtocolClDropPartyComplete</i> can call 
    <b>NdisClDropParty</b> with any valid 
    <i>NdisPartyHandle</i> to one of the remaining parties on the client's active multipoint VC. If only one
    more party remains on its multipoint VC, the client should drop that party by passing its 
    <i>NdisPartyHandle</i> to 
    <a href="netvista.ndisclclosecall">NdisClCloseCall</a>.

To define a <i>ProtocolClDropPartyComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClDropPartyComplete</i> function that is named "MyClDropPartyComplete", use the <b>PROTOCOL_CL_DROP_PARTY_COMPLETE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CL_DROP_PARTY_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_DROP_PARTY_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/6294d8b9-c403-477f-87c8-7a8b36845343">
   ProtocolClDropPartyComplete (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <i>
   ProtocolClDropPartyComplete (NDIS 5.1)</i>) in Windows XP.
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
<a href="netvista.ndiscladdparty">NdisClAddParty</a>
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
<a href="netvista.ndiscmdroppartycomplete">NdisCmDropPartyComplete</a>
</dt>
<dt>
<a href="netvista.ndisfreememory">NdisFreeMemory</a>
</dt>
<dt>
<a href="netvista.ndisfreetonpagedlookasidelist">
   NdisFreeToNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndismcmdroppartycomplete">NdisMCmDropPartyComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_drop_party.md">ProtocolCmDropParty</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_DROP_PARTY_COMPLETE callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
