---
UID : NF:ndis.NdisMResetComplete
title : NdisMResetComplete function
author : windows-driver-content
description : The NdisMResetComplete function returns the final status of a reset request for which the miniport driver previously returned NDIS_STATUS_PENDING.
old-location : netvista\ndismresetcomplete.htm
old-project : netvista
ms.assetid : 3da12a14-a90a-46a6-b67e-55044fdc3ca1
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisMResetComplete function [Network Drivers Starting with Windows Vista], ndis/NdisMResetComplete, netvista.ndismresetcomplete, NdisMResetComplete, miniport_ndis_functions_ref_cea3e0dd-c6cb-49a7-86e3-68b779a355d2.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see    NdisMResetComplete (NDIS 5.1).
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Irql_Miniport_Driver_Function
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : "<= DISPATCH_LEVEL (see Remarks section)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMResetComplete function
The 
  <b>NdisMResetComplete</b> function returns the final status of a reset request for which the miniport driver
  previously returned NDIS_STATUS_PENDING.

## Syntax

````
VOID NdisMResetComplete(
  _In_ NDIS_HANDLE MiniportAdapterHandle,
  _In_ NDIS_STATUS Status,
  _In_ BOOLEAN     AddressingReset
);
````

## Parameters

`MiniportAdapterHandle`

The miniport adapter handle that NDIS originally passed to the 
     <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function.

`Status`

The final status of the reset operation just completed

`AddressingReset`

A Boolean value that is <b>TRUE</b> if NDIS is responsible for restoring the settings for multicast
     addresses, packet filters, and task offload information. In this case, the miniport driver is
     responsible for restoring the rest of the configuration settings for the network interface card (NIC)
     referenced by 
     <i>MiniportAdapterHandle</i> . 
     

If 
     <i>AddressingReset</i> is <b>FALSE</b>, the miniport driver is responsible for restoring all of the
     configuration settings for the NIC.

For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff546572">Hardware Reset</a>.


## Return Value

None

## Remarks

If the 
    <a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> function returns
    NDIS_STATUS_PENDING, the miniport driver must call 
    <b>NdisMResetComplete</b> when it completes the reset operation.

Protocol drivers cannot initiate a reset operation in NDIS 6.0 and later versions.

Some NICs lose all multicast address, packet filter, or functional address information when a soft
    reset is issued. The driver of such a NIC sets 
    <i>AddressingReset</i> to <b>TRUE</b> when it calls 
    <b>NdisMResetComplete</b>, causing NDIS to call its 
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function to
    restore the addressing state. For more information, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff546572">Hardware Reset</a>.

A miniport driver must release any spin lock that it is holding before calling 
    <b>NdisMResetComplete</b>.

In NDIS 6.0 and later, callers of 
    <b>NdisMResetComplete</b> must run at IRQL &lt;= DISPATCH_LEVEL. Otherwise, callers of 
    <b>NdisMResetComplete</b> must run at IRQL = DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see    NdisMResetComplete (NDIS 5.1). Supported in NDIS 5.1, and NDIS 6.0 and later. For NDIS 5.1 drivers, see    NdisMResetComplete (NDIS 5.1). |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |
| **DDI compliance rules** | Irql_Miniport_Driver_Function |

## See Also

<a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a>

<a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMResetComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>