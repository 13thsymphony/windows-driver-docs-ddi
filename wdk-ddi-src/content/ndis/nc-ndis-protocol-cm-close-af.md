---
UID: NC.ndis.PROTOCOL_CM_CLOSE_AF
title: PROTOCOL_CM_CLOSE_AF
author: windows-driver-content
description: The ProtocolCmCloseAf function is a required function that releases per-open resources for an address family that a call manager supports.Note  You must declare the function by using the PROTOCOL_CM_CLOSE_AF type.
old-location: netvista\protocolcmcloseaf.htm
old-project: netvista
ms.assetid: a7a02813-62e4-49c5-abb6-a90f4e092b9f
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   ProtocolCmCloseAf (NDIS 5.1))
   in Windows Vista. Supported for NDIS 5.1 drivers (see 
   ProtocolCmCloseAf (NDIS 5.1))
   in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolCmCloseAf
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
req.iface: 
---

# PROTOCOL_CM_CLOSE_AF callback



## -description
<p>The 
  <i>ProtocolCmCloseAf</i> function is a required function that releases per-open resources for an address
  family that a call manager supports.</p>


## -prototype

````
PROTOCOL_CM_CLOSE_AF ProtocolCmCloseAf;

NDIS_STATUS ProtocolCmCloseAf(
  _In_ NDIS_HANDLE CallMgrAfContext
)
{ ... }
````


## -parameters
<dl>

### -param <i>CallMgrAfContext</i> [in]

<dd>
<p>Specifies the handle to the call manager's per-AF context area, originally supplied to NDIS by the
     call manager's 
     <i>ProtocolCmOpenAf</i> function.</p>
</dd>
</dl>

## -returns
<p><i>ProtocolCmCloseAf</i> returns the status of its operation(s) as one of the following:</p><dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl><p>Indicates that the call manager has successfully released or deactivated any resources that is
       allocated on behalf of the connection-oriented client that opened this instance of the address
       family.</p><dl>
<dt><b>NDIS_STATUS_PENDING</b></dt>
</dl><p>Indicates that the request to close the open instance of the address family will be completed
       asynchronously. The call manager must call 
       <a href="..\ndis\nf-ndis-ndiscmcloseaddressfamilycomplete.md">
       NdisCmCloseAddressFamilyComplete</a> when all such operations have been completed.</p>

<p> </p>

## -remarks
<p><i>ProtocolCmCloseAf</i> releases and/or deactivates any resources that were allocated by the call manager
    in its 
    <a href="..\ndis\nc-ndis-protocol-cm-open-af.md">ProtocolCmOpenAf</a> function. The call
    manager also should undo any other actions it took on behalf of the connection-oriented client when the
    address family was opened by that client.</p>

<p>If there are any outstanding requests or connections still open on an address family stored in the 
    <i>CallMgrAfContext</i>, a call manager can respond to a client's request to close the address family in
    either of the following ways:</p>

<p>The call manager can fail the request with NDIS_STATUS_NOT_ACCEPTED.</p>

<p>The call manager can return NDIS_STATUS_PENDING. After the client has closed all calls and
      deregistered all SAPs, the call manager can then close the address family and call 
      <b>NdisCmCloseAddressFamilyComplete</b> or 
      <a href="..\ndis\nf-ndis-ndismcmcloseaddressfamilycomplete.md">
      NdisMCmCloseAddressFamilyComplete</a> to notify the client. This is the preferred response.</p>

<p>To define a <i>ProtocolCmCloseAf</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ProtocolCmCloseAf</i> function that is named "MyCmCloseAf", use the <b>PROTOCOL_CM_CLOSE_AF</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>PROTOCOL_CM_CLOSE_AF</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_CLOSE_AF</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

<p><i>ProtocolCmCloseAf</i> releases and/or deactivates any resources that were allocated by the call manager
    in its 
    <a href="..\ndis\nc-ndis-protocol-cm-open-af.md">ProtocolCmOpenAf</a> function. The call
    manager also should undo any other actions it took on behalf of the connection-oriented client when the
    address family was opened by that client.</p>

<p>If there are any outstanding requests or connections still open on an address family stored in the 
    <i>CallMgrAfContext</i>, a call manager can respond to a client's request to close the address family in
    either of the following ways:</p>

<p>The call manager can fail the request with NDIS_STATUS_NOT_ACCEPTED.</p>

<p>The call manager can return NDIS_STATUS_PENDING. After the client has closed all calls and
      deregistered all SAPs, the call manager can then close the address family and call 
      <b>NdisCmCloseAddressFamilyComplete</b> or 
      <a href="..\ndis\nf-ndis-ndismcmcloseaddressfamilycomplete.md">
      NdisMCmCloseAddressFamilyComplete</a> to notify the client. This is the preferred response.</p>

<p>To define a <i>ProtocolCmCloseAf</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>ProtocolCmCloseAf</i> function that is named "MyCmCloseAf", use the <b>PROTOCOL_CM_CLOSE_AF</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>PROTOCOL_CM_CLOSE_AF</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CM_CLOSE_AF</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/library/windows/hardware/ff563183">ProtocolCmCloseAf (NDIS 5.1)</a>)
   in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <i>ProtocolCmCloseAf (NDIS 5.1)</i>)
   in Windows XP.</p>
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
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndiscmcloseaddressfamilycomplete.md">
   NdisCmCloseAddressFamilyComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-cm-open-af.md">ProtocolCmOpenAf</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CM_CLOSE_AF callback function%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
