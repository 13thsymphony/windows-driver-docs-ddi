---
UID: NF:ndis.NdisCmRegisterSapComplete
title: NdisCmRegisterSapComplete function
author: windows-driver-content
description: NdisCmRegisterSapComplete returns the final status of a client's request, for which the CM previously returned NDIS_STATUS_PENDING, to register a SAP.
old-location: netvista\ndiscmregistersapcomplete.htm
old-project: netvista
ms.assetid: 0419bbf5-02aa-482f-9e2c-a435302751c4
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisCmRegisterSapComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmRegisterSapComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmRegisterSapComplete (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCmRegisterSapComplete
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_CallManager_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisCmRegisterSapComplete function



## -description
<b>NdisCmRegisterSapComplete</b> returns the final status of a client's request, for which the CM previously
  returned NDIS_STATUS_PENDING, to register a SAP.



## -syntax

````
VOID NdisCmRegisterSapComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE NdisSapHandle,
  _In_ NDIS_HANDLE CallMgrSapContext
);
````


## -parameters

### -param Status [in]

Specifies the final status of the client's original request to register the SAP, either
     NDIS_STATUS_SUCCESS or any CM-determined NDIS_STATUS_<i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisSapHandle [in]

Specifies the NDIS-supplied handle to the SAP if the registration is successful. The call manager
     obtained this handle as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">
     ProtocolCmRegisterSap</a> function.


### -param CallMgrSapContext [in]

Specifies the handle to a caller-supplied resident context area in which the CM maintains state
     for this SAP if the registration is successful. If so, NDIS passes this handle back to the CM in all
     subsequent calls concerning this SAP. If 
     <i>Status</i> is set to something other than NDIS_STATUS_SUCCESS, NDIS ignores this parameter.


## -returns
None


## -remarks
A stand-alone call manager must call 
    <b>NdisCmRegisterSapComplete</b> if its 
    <a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a> function
    returned NDIS_STATUS_PENDING when it was called with the given 
    <i>NdisSapHandle</i> . The call to 
    <b>NdisCmRegisterSapComplete</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_register_sap_complete.md">
    ProtocolClRegisterSapComplete</a> function.

If the call manager sets 
    <i>Status</i> to anything other than NDIS_STATUS_SUCCESS, it should consider the 
    <i>NdisSapHandle</i> invalid as soon as it calls 
    <b>NdisCmRegisterSapComplete</b>. After failing a SAP registration, the CM can release or reuse the
    per-SAP context area that it allocated when 
    <b>NdisCmRegisterSapComplete</b> returns control. NDIS also releases its context for the SAP if the call
    manager fails the registration.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmRegisterSapComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmRegisterSapComplete</b>.


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
   <a href="https://msdn.microsoft.com/f31478ef-a700-4279-a371-dfab4bad6af1">NdisCmRegisterSapComplete (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisCmRegisterSapComplete (NDIS
   5.1)</b>) in Windows XP.

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
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547917">Irql_CallManager_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatefromnpagedlookasidelist.md">
   NdisAllocateFromNPagedLookasideList</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisclregistersap.md">NdisClRegisterSap</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmregistersapcomplete.md">NdisMCmRegisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_register_sap_complete.md">
   ProtocolClRegisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_reg_sap.md">ProtocolCmRegisterSap</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmRegisterSapComplete function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

