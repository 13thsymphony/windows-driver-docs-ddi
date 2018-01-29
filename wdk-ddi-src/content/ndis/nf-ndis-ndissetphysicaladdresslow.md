---
UID : NF:ndis.NdisSetPhysicalAddressLow
title : NdisSetPhysicalAddressLow macro
author : windows-driver-content
description : NdisSetPhysicalAddressLow sets the low-order part of a given physical address to a given value.
old-location : netvista\ndissetphysicaladdresslow.htm
old-project : netvista
ms.assetid : 2454f923-15c5-43c8-8d62-eee000d89a10
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/NdisSetPhysicalAddressLow, NdisSetPhysicalAddressLow macro [Network Drivers Starting with Windows Vista], netvista.ndissetphysicaladdresslow, NdisSetPhysicalAddressLow, miniport_memory_shared_ref_b21e2206-bd6c-47b6-b518-31bcad459bbb.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisSetPhysicalAddressLow (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisSetPhysicalAddressLow (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : ndis.h
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisSetPhysicalAddressLow function
<b>NdisSetPhysicalAddressLow</b> sets the low-order part of a given physical address to a given
  value.

## Syntax

````
VOID NdisSetPhysicalAddressLow(
  [in] NDIS_PHYSICAL_ADDRESS PhysicalAddress,
  [in] ULONG                 Value
);
````

## Parameters

`_PhysicalAddress`

TBD

`_Value`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndis\nf-ndis-ndissetphysicaladdresshigh.md">NdisSetPhysicalAddressHigh</a>

<a href="..\ndis\nf-ndis-ndisgetphysicaladdresslow.md">NdisGetPhysicalAddressLow</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557129">NDIS_PHYSICAL_ADDRESS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisSetPhysicalAddressLow macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>