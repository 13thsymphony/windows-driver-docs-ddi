---
UID : NF:ndis.NdisMCoDeactivateVcComplete
title : NdisMCoDeactivateVcComplete function
author : windows-driver-content
description : NdisMCoDeactivateVcComplete notifies NDIS and the call manager that the miniport driver has finished processing a CM-initiated deactivate-VC request, for which the miniport driver previously returned NDIS_STATUS_PENDING.
old-location : netvista\ndismcodeactivatevccomplete.htm
old-project : netvista
ms.assetid : 8ea36895-4728-45ad-84f7-3517afd2327d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : condis_miniport_ref_b4ad1f67-6e33-45ca-9d55-323aed8820be.xml, NdisMCoDeactivateVcComplete, netvista.ndismcodeactivatevccomplete, ndis/NdisMCoDeactivateVcComplete, NdisMCoDeactivateVcComplete function [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCoDeactivateVcComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCoDeactivateVcComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_MCO_Function
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
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMCoDeactivateVcComplete function
<b>NdisMCoDeactivateVcComplete</b> notifies NDIS and the call manager that the miniport driver has finished
  processing a CM-initiated deactivate-VC request, for which the miniport driver previously returned
  NDIS_STATUS_PENDING.

## Syntax

````
VOID NdisMCoDeactivateVcComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE NdisVcHandle
);
````

## Parameters

`Status`

Specifies the final status of the deactivate-VC operation, which can be NDIS_STATUS_SUCCESS or any
     NDIS_STATUS_
     <i>XXX except</i> NDIS_STATUS_PENDING.

`NdisVcHandle`

Specifies the handle identifying the VC. The caller obtained this handle from its per-VC state,
     designated by the 
     <i>MiniportVcContext</i> passed as an input parameter to its 
     <a href="..\ndis\nc-ndis-miniport_co_deactivate_vc.md">
     MiniportCoDeactivateVc</a> function.


## Return Value

None

## Remarks

A connection-oriented miniport driver must call 
    <b>NdisMCoDeactivateVcComplete</b> if its 
    <i>MiniportCoDeactivateVc</i> function previously returned NDIS_STATUS_PENDING in response to a request to
    deactivate the VC identified by the given 
    <i>NdisVcHandle</i> . The call manager, which initiated the VC deactivation with a call to 
    <a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a>, cannot notify NDIS
    or its client whether transfers have been disabled on the VC until the miniport driver calls 
    <b>NdisMCoDeactivateVcComplete</b>.

Before it deactivates a VC, the miniport driver must complete any pending transfers on the VC. That
    is, the miniport driver must indicate all outstanding receives and transmit all outstanding sends before
    calling 
    <b>NdisMCoDeactivateVcComplete</b>.

A call to 
    <b>NdisMCoDeactivateVcComplete</b> causes NDIS to call the 
    <a href="..\ndis\nc-ndis-protocol_cm_deactivate_vc_complete.md">
    ProtocolCmDeactivateVcComplete</a> function of the call manager that originally requested the VC
    deactivation. Following its call to 
    <b>NdisMCoDeactivateVcComplete</b>, the miniport driver can neither indicate receives nor transmit sends
    on the VC.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCoDeactivateVcComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCoDeactivateVcComplete   (NDIS 5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCoDeactivateVcComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCoDeactivateVcComplete   (NDIS 5.1)) in Windows XP. |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_MCO_Function |

## See Also

<a href="..\ndis\nf-ndis-ndiscmactivatevc.md">NdisCmActivateVc</a>

<a href="..\ndis\nc-ndis-miniport_co_deactivate_vc.md">MiniportCoDeactivateVc</a>

<a href="..\ndis\nf-ndis-ndiscmdeactivatevc.md">NdisCmDeactivateVc</a>

<a href="..\ndis\nc-ndis-protocol_cm_deactivate_vc_complete.md">
   ProtocolCmDeactivateVcComplete</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCoDeactivateVcComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>