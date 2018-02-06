---
UID: NF:ndis.NdisMCmDeregisterSapComplete
title: NdisMCmDeregisterSapComplete macro
author: windows-driver-content
description: NdisMCmDeregisterSapComplete returns the final status of a client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to deregister a SAP.
old-location: netvista\ndismcmderegistersapcomplete.htm
old-project: netvista
ms.assetid: 69524144-fc55-4721-a753-6452566a8b26
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisMCmDeregisterSapComplete, condis_mcm_ref_c7c4035b-8227-418a-895d-9b14027ce4c4.xml, NdisMCmDeregisterSapComplete macro [Network Drivers Starting with Windows Vista], NdisMCmDeregisterSapComplete, netvista.ndismcmderegistersapcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDeregisterSapComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDeregisterSapComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: ndis.h
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisMCmDeregisterSapComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMCmDeregisterSapComplete function
<b>NdisMCmDeregisterSapComplete</b> returns the final status of a client's request, for which the MCM driver
  previously returned NDIS_STATUS_PENDING, to deregister a SAP.

## Syntax

````
VOID NdisMCmDeregisterSapComplete(
  [in] NDIS_STATUS Status,
  [in] NDIS_HANDLE NdisSapHandle
);
````

## Parameters

`_S_`

TBD

`_H_`

TBD


## Return Value

None

## Remarks

<b>NdisMCmDeregisterSapComplete</b> notifies both NDIS and the client that the MCM driver has completed
    the SAP-deregistration request for which its 
    <a href="..\ndis\nc-ndis-protocol_cm_deregister_sap.md">
    ProtocolCmDeregisterSap</a> function previously returned NDIS_STATUS_PENDING.

A call to 
    <b>NdisMCmDeregisterSapComplete</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_deregister_sap_complete.md">
    ProtocolClDeregisterSapComplete</a> function.

The MCM driver should consider the 
    <i>NdisSapHandle</i> invalid when 
    <b>NdisMCmDeregisterSapComplete</b> returns control.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDeregisterSapComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDeregisterSapComplete</b> instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDeregisterSapComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDeregisterSapComplete   (NDIS 5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDeregisterSapComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDeregisterSapComplete   (NDIS 5.1)) in Windows XP. |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | ndis.h |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_MCM_Function |

## See Also

<a href="..\ndis\nf-ndis-ndiscmderegistersapcomplete.md">NdisCmDeregisterSapComplete</a>

<a href="..\ndis\nc-ndis-protocol_cl_deregister_sap_complete.md">
   ProtocolClDeregisterSapComplete</a>

<a href="..\ndis\nc-ndis-protocol_cm_deregister_sap.md">ProtocolCmDeregisterSap</a>

<a href="..\ndis\nf-ndis-ndisclderegistersap.md">NdisClDeregisterSap</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmDeregisterSapComplete macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>