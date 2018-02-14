---
UID: NF:ndis.NdisSetPhysicalAddressHigh
title: NdisSetPhysicalAddressHigh macro
author: windows-driver-content
description: NdisSetPhysicalAddressHigh sets the high-order part of a given physical address to a given value.
old-location: netvista\ndissetphysicaladdresshigh.htm
old-project: netvista
ms.assetid: bbe58583-ea65-4920-9056-ab46bd881618
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisSetPhysicalAddressHigh macro [Network Drivers Starting with Windows Vista], miniport_memory_shared_ref_4644a620-5ec7-449e-9886-ddee46d9ff2a.xml, ndis/NdisSetPhysicalAddressHigh, NdisSetPhysicalAddressHigh, netvista.ndissetphysicaladdresshigh
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisSetPhysicalAddressHigh   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisSetPhysicalAddressHigh   (NDIS 5.1)) in Windows XP.
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
req.lib: ndis.h
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisSetPhysicalAddressHigh
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisSetPhysicalAddressHigh function
<b>NdisSetPhysicalAddressHigh</b> sets the high-order part of a given physical address to a given
  value.

## Syntax

````
VOID NdisSetPhysicalAddressHigh(
  [in] NDIS_PHYSICAL_ADDRESS PhysicalAddress,
  [in] ULONG                 Value
);
````

## Parameters

`_PhysicalAddress`

Specifies a physical address of an OS-dependent size.

`_Value`

Specifies the value to be written into the high-order part of the address.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisSetPhysicalAddressHigh   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisSetPhysicalAddressHigh   (NDIS 5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisSetPhysicalAddressHigh   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisSetPhysicalAddressHigh   (NDIS 5.1)) in Windows XP. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | ndis.h |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndisgetphysicaladdresshigh.md">NdisGetPhysicalAddressHigh</a>



<a href="..\ndis\nf-ndis-ndissetphysicaladdresslow.md">NdisSetPhysicalAddressLow</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557129">NDIS_PHYSICAL_ADDRESS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisSetPhysicalAddressHigh macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>