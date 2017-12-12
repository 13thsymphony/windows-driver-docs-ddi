---
UID: NF.ndis.NdisMCmRegisterSapComplete
title: NdisMCmRegisterSapComplete macro
author: windows-driver-content
description: NdisMCmRegisterSapComplete returns the final status of a client's request, for which the MCM driver's ProtocolCmRegisterSap function previously returned NDIS_STATUS_PENDING, to register a SAP.
old-location: netvista\ndismcmregistersapcomplete.htm
old-project: netvista
ms.assetid: 53f94e25-ca6c-4230-8447-d36774322dc7
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisMCmRegisterSapComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmRegisterSapComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmRegisterSapComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCmRegisterSapComplete
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

# NdisMCmRegisterSapComplete macro



## -description
<b>NdisMCmRegisterSapComplete</b> returns the final status of a client's request, for which the MCM driver's
  
  <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a> function
  previously returned NDIS_STATUS_PENDING, to register a SAP.



## -syntax

````
VOID NdisMCmRegisterSapComplete(
  [in] NDIS_STATUS Status,
  [in] NDIS_HANDLE NdisSapHandle,
  [in] NDIS_HANDLE CallMgrSapContext
);
````


## -parameters

### -param Status [in]

Specifies the final status for the client's original request to register the SAP, either
     NDIS_STATUS_SUCCESS or any caller-determined NDIS_STATUS_<i>XXX</i><u>except</u> NDIS_STATUS_PENDING.


### -param NdisSapHandle [in]

Specifies the NDIS-supplied handle to the SAP if the registration is successful. The call manager
     obtained this handle as an input parameter to its 
     <i>ProtocolCmRegisterSap</i> function.


### -param CallMgrSapContext [in]

Specifies the handle to a caller-supplied resident context area in which the MCM driver maintains
     state for this SAP if the registration is successful. If so, NDIS passes this handle back to the to the
     MCM driver in all subsequent calls concerning this SAP. If 
     <i>Status</i> is set to something other than NDIS_STATUS_SUCCESS, NDIS ignores this parameter.


## -remarks
An MCM driver must call 
    <b>NdisMCmRegisterSapComplete</b> if its 
    <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a> function
    returned NDIS_STATUS_PENDING when it was called with the given 
    <i>NdisSapHandle</i> . The call to 
    <b>NdisMCmRegisterSapComplete</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_register_sap_complete.md">
    ProtocolClRegisterSapComplete</a> function.

If the MCM driver sets 
    <i>Status</i> to anything other than NDIS_STATUS_SUCCESS, it should consider the 
    <i>NdisSapHandle</i> invalid when 
    <b>NdisMCmRegisterSapComplete</b> returns control. After failing a SAP registration, the CM can release or
    reuse the per-SAP context area, if any, that it already allocated. NDIS also releases its context for the
    SAP if the MCM driver fails the registration.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmRegisterSapComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmRegisterSapComplete</b> instead.


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
   <a href="https://msdn.microsoft.com/4ff3cd15-daa9-41b3-8a38-edebf3f2fd94">NdisMCmRegisterSapComplete
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisMCmRegisterSapComplete
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
<a href="netvista.ndisallocatefromnpagedlookasidelist">
   NdisAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="netvista.ndisclregistersap">NdisClRegisterSap</a>
</dt>
<dt>
<a href="netvista.ndiscmregistersapcomplete">NdisCmRegisterSapComplete</a>
</dt>
<dt>
<a href="netvista.ndismcmdispatchincomingcall">NdisMCmDispatchIncomingCall</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_register_sap_complete.md">
   ProtocolClRegisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmRegisterSapComplete macro%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

