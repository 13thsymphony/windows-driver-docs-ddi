---
UID: NC.ndis.PROTOCOL_CL_DEREGISTER_SAP_COMPLETE
title: PROTOCOL_CL_DEREGISTER_SAP_COMPLETE
author: windows-driver-content
description: The ProtocolClDeregisterSapComplete function is used by connection-oriented NDIS clients.
old-location: netvista\protocolclderegistersapcomplete.htm
old-project: netvista
ms.assetid: 93f8f74a-8ad4-42ea-83cf-ddfcd7f55ce6
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       ProtocolClDeregisterSapComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       ProtocolClDeregisterSapComplete (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolClDeregisterSapComplete
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

# PROTOCOL_CL_DEREGISTER_SAP_COMPLETE callback



## -description
The 
  <i>ProtocolClDeregisterSapComplete</i> function is used by connection-oriented NDIS clients.
  Connection-oriented NDIS clients that accept incoming calls must have 
  <i>ProtocolClDeregisterSapComplete</i> functions to complete the asynchronous operations that they initiate
  with 
  <a href="netvista.ndisclderegistersap">NdisClDeregisterSap</a>. Otherwise, such a
  protocol driver's registered 
  <i>ProtocolClDeregisterSapComplete</i> function can simply return control.



## -prototype

````
PROTOCOL_CL_DEREGISTER_SAP_COMPLETE ProtocolClDeregisterSapComplete;

VOID ProtocolClDeregisterSapComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE ProtocolSapContext
)
{ ... }
````


## -parameters

### -param Status [in]

Specifies the final status of the client's request to deregister its SAP, which can be one of the
     following:
     




### -param NDIS_STATUS_SUCCESS

The SAP was closed. The 
       <i>NdisSapHandle</i> that represented the client's previously registered SAP, which the client stored
       in its 
       <i>ProtocolSapContext</i> area, is now invalid.


### -param NDIS_STATUS_FAILURE

NDIS had marked the state of the AF as "closing," so the associated SAP represented by the 
       <i>NdisSapHandle</i> was already released when the client's call to 
       <a href="netvista.ndisclderegistersap">
       NdisClDeregisterSap</a> occurred.


### -param NDIS_STATUS_XXX

The call manager failed the request to close the SAP for some CM-determined reason, and NDIS
       propagated the status returned by its 
       <a href="..\ndis\nc-ndis-protocol_cm_deregister_sap.md">
       ProtocolCmDeregisterSap</a> function to the client.

</dd>
</dl>

### -param ProtocolSapContext [in]

Specifies the client-supplied handle to its per-SAP context area, originally passed to NDIS with 
     <b>NdisClRegisterSap</b>. After the call manager has successfully deregistered this SAP, the client can
     release its context area or prepare this context area for reuse.


## -returns
None


## -remarks
A call to 
    <i>ProtocolClDeregisterSapComplete</i> indicates that the client's preceding call to 
    <a href="netvista.ndisclderegistersap">NdisClDeregisterSap</a> has been processed
    by the call manager.

Unless the call manager failed the deregistration for some CM-determined reason, the client should
    consider the 
    <i>NdisSapHandle</i> invalid when 
    <i>ProtocolClDeregisterSapComplete</i> is called. Consequently, 
    <i>ProtocolClDeregisterSapComplete</i> can release the per-SAP context area that the client allocated or
    prepare it for reuse in a subsequent call to 
    <a href="netvista.ndisclregistersap">NdisClRegisterSap</a>.

To define a <i>ProtocolClDeregisterSapComplete</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>ProtocolClDeregisterSapComplete</i> function that is named "MyClDeregisterSapComplete", use the <b>PROTOCOL_CL_DEREGISTER_SAP_COMPLETE</b> type as shown in this code example:

Then, implement your function as follows:

The <b>PROTOCOL_CL_DEREGISTER_SAP_COMPLETE</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>PROTOCOL_CL_DEREGISTER_SAP_COMPLETE</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/14b9154a-041e-4a49-9a89-c04ef6696bf7">
   ProtocolClDeregisterSapComplete (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <i>
   ProtocolClDeregisterSapComplete (NDIS 5.1)</i>) in Windows XP.

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
<a href="netvista.ndiscmderegistersapcomplete">NdisCmDeregisterSapComplete</a>
</dt>
<dt>
<a href="netvista.ndisfreememory">NdisFreeMemory</a>
</dt>
<dt>
<a href="netvista.ndisfreetonpagedlookasidelist">
   NdisFreeToNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndismcmderegistersapcomplete">NdisMCmDeregisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_deregister_sap.md">ProtocolCmDeregisterSap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20PROTOCOL_CL_DEREGISTER_SAP_COMPLETE callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

