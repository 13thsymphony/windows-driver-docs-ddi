---
UID: NF.ndis.NdisCmModifyCallQoSComplete
title: NdisCmModifyCallQoSComplete function
author: windows-driver-content
description: NdisCmModifyCallQoSComplete indicates the completion of the client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to modify the quality of service on a VC.
old-location: netvista\ndiscmmodifycallqoscomplete.htm
old-project: netvista
ms.assetid: 8489dc63-8e92-45c9-b4a8-593b511743b0
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: NdisCmModifyCallQoSComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmModifyCallQoSComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmModifyCallQoSComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCmModifyCallQoSComplete
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
---

# NdisCmModifyCallQoSComplete function



## -description
<b>NdisCmModifyCallQoSComplete</b> indicates the completion of the client's request, for which the call
  manager previously returned NDIS_STATUS_PENDING, to modify the quality of service on a VC.



## -syntax

````
VOID NdisCmModifyCallQoSComplete(
  _In_ NDIS_STATUS         Status,
  _In_ NDIS_HANDLE         NdisVcHandle,
  _In_ PCO_CALL_PARAMETERS CallParameters
);
````


## -parameters

### -param Status [in]

Specifies the final status of the client's request to modify the QoS on this VC, either
     NDIS_STATUS_SUCCESS or any CM-determined NDIS_STATUS_
     <i>XXX</i> except NDIS_STATUS_PENDING.


### -param NdisVcHandle [in]

Specifies the handle to the VC, obtained from the 
     <i>CallMgrVcContext</i> passed in to the CM's 
     <a href="..\ndis\nc-ndis-protocol_cm_modify_qos_call.md">
     ProtocolCmModifyCallQoS</a> function for this request.


### -param CallParameters [in]

Pointer to a structure of type 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a> specifying a QoS
     acceptable to the call manager and underlying miniport driver if 
     <i>Status</i> is set to NDIS_STATUS_SUCCESS.


## -returns
None


## -remarks
A call to 
    <b>NdisCmModifyCallQoSComplete</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_modify_call_qos_complete.md">
    ProtocolClModifyCallQoSComplete</a> function.

Because the CM can modify the client-supplied call parameters that were input to its 
    <a href="..\ndis\nc-ndis-protocol_cm_modify_qos_call.md">
    ProtocolCmModifyCallQoS</a> function before it calls 
    <b>NdisCmModifyCallQoSComplete</b>, the client's 
    <i>ProtocolClModifyCallQoSComplete</i> function examines the QoS to determine whether it is acceptable to
    the client. 
    <i>ProtocolClModifyCallQoSComplete</i> simply returns control if the client accepts the given call
    parameters. Otherwise, the client tears down the call.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmModifyCallQoSComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmModifyCallQoSComplete</b> instead.


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
   <a href="https://msdn.microsoft.com/5479ab9b-c3e9-4bc1-9ce1-bca143c67601">NdisCmModifyCallQoSComplete
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisCmModifyCallQoSComplete
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
<a href="devtest.ndis_irql_callmanager_function">Irql_CallManager_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndisclmodifycallqos">NdisClModifyCallQoS</a>
</dt>
<dt>
<a href="netvista.ndismcmmodifycallqoscomplete">NdisMCmModifyCallQosComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_modify_call_qos_complete.md">
   ProtocolClModifyCallQoSComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_modify_qos_call.md">ProtocolCmModifyCallQoS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmModifyCallQoSComplete function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

