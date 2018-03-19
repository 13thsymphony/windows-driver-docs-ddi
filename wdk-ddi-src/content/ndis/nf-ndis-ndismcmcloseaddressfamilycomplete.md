---
UID: NF:ndis.NdisMCmCloseAddressFamilyComplete
title: NdisMCmCloseAddressFamilyComplete macro
author: windows-driver-content
description: NdisMCmCloseAddressFamilyComplete returns the final status of a client's request, for which the MCM driver returned NDIS_STATUS_PENDING, to close the AF.
old-location: netvista\ndismcmcloseaddressfamilycomplete.htm
old-project: netvista
ms.assetid: be551557-06db-4fc9-bdcb-030e621e205a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMCmCloseAddressFamilyComplete, NdisMCmCloseAddressFamilyComplete macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_beab4fb5-32b1-4188-9e6a-47f286386919.xml, ndis/NdisMCmCloseAddressFamilyComplete, netvista.ndismcmcloseaddressfamilycomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisMCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see         NdisMCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows XP.
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
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisMCmCloseAddressFamilyComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMCmCloseAddressFamilyComplete function
<b>NdisMCmCloseAddressFamilyComplete</b> returns the final status of a client's request, for which the MCM
  driver returned NDIS_STATUS_PENDING, to close the AF.

## Syntax

````
VOID NdisMCmCloseAddressFamilyComplete(
  [in] NDIS_STATUS Status,
  [in] NDIS_HANDLE NdisAfHandle
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

An MCM driver must call 
    <b>NdisMCmCloseAddressFamilyComplete</b> if its 
    <a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a> function previously
    returned NDIS_STATUS_PENDING for the given 
    <i>NdisAfHandle</i> . The client, which initiated the pended close-AF operation with a call to 
    <a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>, cannot
    release the resources it allocated to track communications on the AF until the MCM driver's call to 
    <b>NdisMCmCloseAddressFamilyComplete</b>.

A call to 
    <b>NdisMCmCloseAddressFamilyComplete</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">
    ProtocolClCloseAfComplete</a> function.

The MCM driver cannot subsequently use the 
    <i>NdisAfHandle</i>, which is invalid for the MCM driver when 
    <b>NdisMCmCloseAddressFamilyComplete</b> returns control.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmCloseAddressFamilyComplete</b>. Stand-alone call managers, which register themselves with NDIS
    as protocol drivers, call 
    <b>NdisCmCloseAddressFamilyComplete</b> instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisMCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see         NdisMCmCloseAddressFamilyComplete (NDIS 5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_MCM_Function |

## See Also

<a href="..\ndis\nc-ndis-protocol_cl_close_af_complete.md">ProtocolClCloseAfComplete</a>



<a href="..\ndis\nf-ndis-ndiscmcloseaddressfamilycomplete.md">
   NdisCmCloseAddressFamilyComplete</a>



<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>



<a href="..\ndis\nc-ndis-protocol_cm_close_af.md">ProtocolCmCloseAf</a>



<a href="..\ndis\nf-ndis-ndisclcloseaddressfamily.md">NdisClCloseAddressFamily</a>