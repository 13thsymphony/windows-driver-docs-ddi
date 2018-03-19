---
UID: NF:ndis.NdisIMAssociateMiniport
title: NdisIMAssociateMiniport function
author: windows-driver-content
description: The NdisIMAssociateMiniport function informs NDIS that the specified lower and upper interfaces for miniport and protocol drivers respectively belong to the same intermediate driver.
old-location: netvista\ndisimassociateminiport.htm
old-project: netvista
ms.assetid: b2c46419-644b-4ad4-aa50-7c6e541638aa
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisIMAssociateMiniport, NdisIMAssociateMiniport function [Network Drivers Starting with Windows Vista], intermediate_ref_2f9545a6-262c-4347-b192-16ea23314410.xml, ndis/NdisIMAssociateMiniport, netvista.ndisimassociateminiport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisIMAssociateMiniport (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisIMAssociateMiniport (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_IM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisIMAssociateMiniport
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisIMAssociateMiniport function
The
  <b>NdisIMAssociateMiniport</b> function informs NDIS that the specified lower and upper interfaces for
  miniport and protocol drivers respectively belong to the same intermediate driver.

## Syntax

````
VOID NdisIMAssociateMiniport(
  _In_ NDIS_HANDLE DriverHandle,
  _In_ NDIS_HANDLE ProtocolHandle
);
````

## Parameters

`DriverHandle`

The handle to the miniport driver interface that the 
     <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
     NdisMRegisterMiniportDriver</a> function returns.

`ProtocolHandle`

The handle to the protocol interface that the 
     <a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">
     NdisRegisterProtocolDriver</a> function returns.


## Return Value

None

## Remarks

Any NDIS intermediate driver that exports both 
    <i>MiniportXxx</i> and 
    <i>ProtocolXxx</i> functions calls 
    <b>NdisIMAssociateMiniport</b> to inform the NDIS library about its miniport upper edge and its protocol
    lower edge. Such an intermediate driver calls 
    <b>NdisIMAssociateMiniport</b> during its 
    <a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a> routine. For more information about 
    <b>DriverEntry</b>, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff548818">DriverEntry of NDIS
    Intermediate Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisIMAssociateMiniport (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisIMAssociateMiniport (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_IM_Function |

## See Also

<a href="..\wudfwdm\nc-wudfwdm-driver_initialize.md">DriverEntry</a>



<a href="..\ndis\nf-ndis-ndisregisterprotocoldriver.md">NdisRegisterProtocolDriver</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>