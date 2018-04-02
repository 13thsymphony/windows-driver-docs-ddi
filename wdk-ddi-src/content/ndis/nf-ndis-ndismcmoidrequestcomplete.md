---
UID: NF:ndis.NdisMCmOidRequestComplete
title: NdisMCmOidRequestComplete macro
author: windows-driver-content
description: The NdisMCmOidRequestComplete function returns the final status of a CoNDIS OID requestthat a miniport call manager (MCM) driver's ProtocolCoOidRequest function previously returned NDIS_STATUS_PENDING for.
old-location: netvista\ndismcmoidrequestcomplete.htm
old-project: netvista
ms.assetid: 4c45be9f-3d07-4150-830a-3aa6d74531ff
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMCmOidRequestComplete, NdisMCmOidRequestComplete macro [Network Drivers Starting with Windows Vista], condis_request_ref_fc46ea1a-b820-4f1d-b986-e879adb27ad6.xml, ndis/NdisMCmOidRequestComplete, netvista.ndismcmoidrequestcomplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	NdisMCmOidRequestComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMCmOidRequestComplete function
The 
  <b>NdisMCmOidRequestComplete</b> function returns the final status of a CoNDIS OID requestthat a miniport
  call manager (MCM) driver's 
  <a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">ProtocolCoOidRequest</a> function
  previously returned NDIS_STATUS_PENDING for.

## Syntax

```
void NdisMCmOidRequestComplete(
   _AH_,
   _VH_,
   _PH_,
   _R_,
   _S_
);
```

## Parameters

`_AH_`

TBD

`_VH_`

TBD

`_PH_`

TBD

`_R_`

TBD

`_S_`

TBD


## Return Value

None

## Remarks

A CoNDIS MCM that returns NDIS_STATUS_PENDING from its 
    <a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">ProtocolCoOidRequest</a> function must
    call the 
    <b>NdisMCmOidRequestComplete</b> function after the MCM has finished the OID request operation.

After the MCM calls 
    <b>NdisMCmOidRequestComplete</b>, NDIS calls the 
    <a href="https://msdn.microsoft.com/16883c64-3cc6-4f50-8be7-7c58c422a717">
    ProtocolCoOidRequestComplete</a> function of the CoNDIS client that originally called the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a> function.

For more information about the OIDs defined to use with CONDIS drivers, see 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566707">NDIS OIDs</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_MCM_Function |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566710">NDIS_OID_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561711">NdisCoOidRequest</a>



<a href="https://msdn.microsoft.com/8247396f-8781-45da-aba1-a31a2a26a46f">ProtocolCoOidRequest</a>



<a href="https://msdn.microsoft.com/16883c64-3cc6-4f50-8be7-7c58c422a717">
   ProtocolCoOidRequestComplete</a>