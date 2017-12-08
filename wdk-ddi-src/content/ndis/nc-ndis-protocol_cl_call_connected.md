---
UID: NC.ndis.PROTOCOL_CL_CALL_CONNECTED
title: PROTOCOL_CL_CALL_CONNECTED
author: windows-driver-content
description: The ProtocolClCallConnected function is used by connection-oriented NDIS clients that accept incoming calls.
old-location: netvista\protocolclcallconnected.htm
old-project: netvista
ms.assetid: 675b2066-6a65-47cf-bde7-3c843f97c960
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    ProtocolClCallConnected (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    ProtocolClCallConnected (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolClCallConnected
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

# PROTOCOL_CL_CALL_CONNECTED callback



## -description
The 
  <i>ProtocolClCallConnected</i> function is used by connection-oriented NDIS clients that accept incoming
  calls. Such clients must have 
  <i>ProtocolClCallConnected</i> functions. Otherwise, such a protocol driver's registered 
  <i>ProtocolClCallConnected</i> function can simply return control.


## -prototype

````
PROTOCOL_CL_CALL_CONNECTED ProtocolClCallConnected;

VOID ProtocolClCallConnected(
  _In_ NDIS_HANDLE ProtocolVcContext
)
{ ... }
````


## -parameters

### -param ProtocolVcContext [in]

Specifies the client's handle to its per-VC context area. The client originally returned this
     handle to NDIS from its 
     <a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a> function.

## -returns
None

## -remarks
When 
    <i>ProtocolClCallConnected</i> is called, the call manager has successfully completed the final handshake
    on an incoming call offer previously accepted by the client's 
    <i>ProtocolClIncomingCall</i> function, which already set up the call parameters for this connection at 
    <i>ProtocolVcContext</i> .

The call to 
    <i>ProtocolClCallConnected</i> indicates that data transfers, whether incoming or outgoing, now can be
    done on the VC. 
    <i>ProtocolClCallConnected</i> should ensure that the client is ready to make or accept transfers on the
    VC before it returns control.

To define a <i>ProtocolClCallConnected</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClCallConnected</i> function that is named "MyClCallConnected", use the <b>PROTOCOL_CL_CALL_CONNECTED</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CL_CALL_CONNECTED</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_CALL_CONNECTED</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/0ed5beb0-9671-431e-a971-f94db1626dbf">ProtocolClCallConnected (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <i>ProtocolClCallConnected (NDIS
   5.1)</i>) in Windows XP.
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
<a href="netvista.ndiscmdispatchcallconnected">NdisCmDispatchCallConnected</a>
</dt>
<dt>
<a href="netvista.ndiscosendnetbufferlists">NdisCoSendNetBufferLists</a>
</dt>
<dt>
<a href="netvista.ndismcmdispatchcallconnected">NdisMCmDispatchCallConnected</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_incoming_call.md">ProtocolClIncomingCall</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_create_vc.md">ProtocolCoCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_co_receive_net_buffer_lists.md">
   ProtocolCoReceiveNetBufferLists</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_CALL_CONNECTED callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
