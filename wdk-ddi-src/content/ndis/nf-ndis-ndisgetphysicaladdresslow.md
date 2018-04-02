---
UID: NF:ndis.NdisGetPhysicalAddressLow
title: NdisGetPhysicalAddressLow macro
author: windows-driver-content
description: NdisGetPhysicalAddressLow returns the low-order part of a given physical address.
old-location: netvista\ndisgetphysicaladdresslow.htm
old-project: netvista
ms.assetid: a2e9e398-7b47-49eb-b587-7c42a0162f90
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisGetPhysicalAddressLow, NdisGetPhysicalAddressLow macro [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_20e686ee-bdd4-484d-b3c5-af6bbb764059.xml, ndis/NdisGetPhysicalAddressLow, netvista.ndisgetphysicaladdresslow
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetPhysicalAddressLow (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetPhysicalAddressLow (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisGetPhysicalAddressLow
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisGetPhysicalAddressLow function
<b>NdisGetPhysicalAddressLow</b> returns the low-order part of a given physical address.

## Syntax

```
void NdisGetPhysicalAddressLow(
   _PhysicalAddress
);
```

## Parameters

`_PhysicalAddress`

Specifies a physical address of an OS-dependent size.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetPhysicalAddressLow (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetPhysicalAddressLow (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557129">NDIS_PHYSICAL_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562650">NdisGetPhysicalAddressHigh</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564556">NdisSetPhysicalAddressLow</a>