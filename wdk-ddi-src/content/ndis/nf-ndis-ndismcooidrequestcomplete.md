---
UID: NF:ndis.NdisMCoOidRequestComplete
title: NdisMCoOidRequestComplete function
author: windows-driver-content
description: The NdisMCoOidRequestComplete function returns the final status of an OID requestthat a miniport driver's MiniportCoOidRequest function returned NDIS_STATUS_PENDING for.
old-location: netvista\ndismcooidrequestcomplete.htm
old-project: netvista
ms.assetid: 18242351-3dec-40df-b112-2335253903d2
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMCoOidRequestComplete, NdisMCoOidRequestComplete function [Network Drivers Starting with Windows Vista], condis_request_ref_516edd5f-ceae-4330-87b1-48a3a383e736.xml, ndis/NdisMCoOidRequestComplete, netvista.ndismcooidrequestcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCO_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMCoOidRequestComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMCoOidRequestComplete function
The 
  <b>NdisMCoOidRequestComplete</b> function returns the final status of an OID requestthat a miniport driver's
  
  <a href="https://msdn.microsoft.com/903bcdc5-9d42-4067-a054-057edc95ccf7">MiniportCoOidRequest</a> function
  returned NDIS_STATUS_PENDING for.

## Syntax

```
void NdisMCoOidRequestComplete(
  NDIS_HANDLE       MiniportAdapterHandle,
  NDIS_HANDLE       NdisMiniportVcHandle,
  PNDIS_OID_REQUEST Request,
  NDIS_STATUS       Status
);
```

## Parameters

`MiniportAdapterHandle`

A miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.

`NdisMiniportVcHandle`

TBD

`Request`

TBD

`Status`

The final status of the request operation, either NDIS_STATUS_SUCCESS,
     NDIS_STATUS_REQUEST_ABORTED, or any driver-determined NDIS_STATUS_<i>XXX</i> value 
     <u>except</u> NDIS_STATUS_PENDING.


## Return Value

None

## Remarks

A CoNDIS miniport driver that returns NDIS_STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/903bcdc5-9d42-4067-a054-057edc95ccf7">MiniportCoOidRequest</a> function must
    call 
    <b>NdisMCoOidRequestComplete</b> after the miniport driver has finished the request operation.

A call to 
    <b>NdisMCoOidRequestComplete</b> causes a call to the 
    <a href="https://msdn.microsoft.com/16883c64-3cc6-4f50-8be7-7c58c422a717">
    ProtocolCoOidRequestComplete</a> function of the overlying driver that called the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_MCO_Function |

## See Also

<a href="https://msdn.microsoft.com/99eaba29-ce17-4e79-878e-5fdf7411e56c">MiniportCoCreateVc</a>



<a href="https://msdn.microsoft.com/903bcdc5-9d42-4067-a054-057edc95ccf7">MiniportCoOidRequest</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a>



<a href="https://msdn.microsoft.com/16883c64-3cc6-4f50-8be7-7c58c422a717">
   ProtocolCoOidRequestComplete</a>