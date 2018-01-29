---
UID : NF:ndis.NdisClModifyCallQoS
title : NdisClModifyCallQoS function
author : windows-driver-content
description : NdisClModifyCallQoS requests a change in the quality of service on a connection.
old-location : netvista\ndisclmodifycallqos.htm
old-project : netvista
ms.assetid : c31449a6-e275-480c-83ea-8575fda73cd9
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisClModifyCallQoS function [Network Drivers Starting with Windows Vista], ndis/NdisClModifyCallQoS, netvista.ndisclmodifycallqos, NdisClModifyCallQoS, condis_client_ref_55b0158f-e91e-4be8-818b-ade726db0f61.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisClModifyCallQoS (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisClModifyCallQoS (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Protocol_Driver_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisClModifyCallQoS function
<b>NdisClModifyCallQoS</b> requests a change in the quality of service on a connection.

## Syntax

````
NDIS_STATUS NdisClModifyCallQoS(
  _In_ NDIS_HANDLE         NdisVcHandle,
  _In_ PCO_CALL_PARAMETERS CallParameters
);
````

## Parameters

`NdisVcHandle`

Specifies the handle to the VC for which the client wants to modify the QoS. The client originally
     obtained this handle by calling 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>, and, more recently,
     retrieved this handle from its per-VC state area.

`CallParameters`

Pointer to a structure of type CO_CALL_PARAMETERS that specifies the new QoS requested by the
     caller.


## Return Value

When 
     <b>NdisClModifyCallQoS</b> returns anything other than NDIS_STATUS_PENDING, the client should make an
     internal call to its 
     <mshelp:link keywords="netvista.protocolclmodifycallqoscomplete" tabindex="0"><i>
     ProtocolClModifyCallQoSComplete</i></mshelp:link> function. Otherwise, NDIS calls the client's 
     <i>ProtocolClModifyCallQoSComplete</i> function when this operation is completed.

## Remarks

A call to 
    <b>NdisClModifyCallQoS</b> causes NDIS to call the CM's 
    <mshelp:link keywords="netvista.protocolcmmodifycallqos" tabindex="0"><i>
    ProtocolCmModifyCallQoS</i></mshelp:link> function, which, in turn, calls 
    <a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a> to notify the underlying
    miniport driver to change the call parameters if the requested QoS change can be made.

If the call manager does not accept the client's proposed QoS change, the client either can continue
    using the unchanged QoS for the call or can tear down the call. If the client and call manager cannot
    agree on the QoS for a particular call, the creator of the VC is responsible for initiating the teardown
    of the VC.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | Irql_Protocol_Driver_Function |

## See Also

<mshelp:link keywords="netvista.protocolclmodifycallqoscomplete" tabindex="0"><i>
   ProtocolClModifyCallQoSComplete</i></mshelp:link>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545384">CO_CALL_PARAMETERS</a>

<a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>

<a href="..\ndis\nf-ndis-ndiscmmodifycallqoscomplete.md">NdisCmModifyCallQoSComplete</a>

<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>

<a href="..\ndis\nc-ndis-miniport_co_activate_vc.md">MiniportCoActivateVc</a>

<a href="..\ndis\nc-ndis-protocol_cm_modify_qos_call.md">ProtocolCmModifyCallQoS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisClModifyCallQoS function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>