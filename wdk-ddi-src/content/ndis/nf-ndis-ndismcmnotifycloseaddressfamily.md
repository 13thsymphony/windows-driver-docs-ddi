---
UID : NF:ndis.NdisMCmNotifyCloseAddressFamily
title : NdisMCmNotifyCloseAddressFamily macro
author : windows-driver-content
description : The NdisMCmNotifyCloseAddressFamily function notifies NDIS that a specified address family (AF) that is associated with a miniport call manager (MCM) should be closed and NDIS should notify any affected CoNDIS clients.
old-location : netvista\ndismcmnotifycloseaddressfamily.htm
old-project : netvista
ms.assetid : 47b0b1da-e29b-45cc-921b-69d630670b44
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/NdisMCmNotifyCloseAddressFamily, condis_mcm_ref_448486f3-1eeb-4f45-b764-6fd4ab06b63e.xml, NdisMCmNotifyCloseAddressFamily, NdisMCmNotifyCloseAddressFamily macro [Network Drivers Starting with Windows Vista], netvista.ndismcmnotifycloseaddressfamily
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Desktop
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_MCM_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : ndis.h
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMCmNotifyCloseAddressFamily function
The 
  <b>NdisMCmNotifyCloseAddressFamily</b> function notifies NDIS that a specified address family (AF) that is
  associated with a miniport call manager (MCM) should be closed and NDIS should notify any affected CoNDIS
  clients.

## Syntax

````
NDIS_STATUS NdisMCmNotifyCloseAddressFamily(
  [in] NDIS_HANDLE NdisAfHandle
);
````

## Parameters

`_AH_`

TBD


## Return Value

None

## Remarks

MCMs, which register as NDIS miniport drivers by calling the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function, can call the 
    <b>NdisMCmNotifyCloseAddressFamily</b> function. Stand-alone call managers instead call the 
    <a href="..\ndis\nf-ndis-ndiscmnotifycloseaddressfamily.md">
    NdisCmNotifyCloseAddressFamily</a> function.

To close an AF for a miniport adapter, the MCM should call 
    <b>NdisMCmNotifyCloseAddressFamily</b> from its 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function. NDIS
    subsequently calls the 
    <a href="..\ndis\nc-ndis-protocol_cl_notify_close_af.md">
    ProtocolClNotifyCloseAf</a> function of the client that has the specified AF open.

If 
    <b>NdisMCmNotifyCloseAddressFamily</b> returns NDIS_STATUS_PENDING, NDIS calls the MCM's 
    <a href="..\ndis\nc-ndis-protocol_cm_notify_close_af_complete.md">
    ProtocolCmNotifyCloseAfComplete</a> function after the client completes the AF close operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | ndis.h |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_MCM_Function |

## See Also

<a href="..\ndis\nf-ndis-ndiscmnotifycloseaddressfamily.md">
   NdisCmNotifyCloseAddressFamily</a>

<a href="..\ndis\nc-ndis-protocol_cl_notify_close_af.md">ProtocolClNotifyCloseAf</a>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="..\ndis\nc-ndis-protocol_cm_notify_close_af_complete.md">
   ProtocolCmNotifyCloseAfComplete</a>

<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>

<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmNotifyCloseAddressFamily macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>