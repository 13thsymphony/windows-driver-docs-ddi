---
UID: NF:ndis.NdisRetrieveUlong
title: NdisRetrieveUlong macro
author: windows-driver-content
description: The NdisRetrieveUlong function retrieves a ULONG value from the source address, avoiding alignment faults.
old-location: netvista\ndisretrieveulong.htm
old-project: netvista
ms.assetid: 41788885-d8a1-4459-82a0-261b39862530
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NdisRetrieveUlong, NdisRetrieveUlong macro [Network Drivers Starting with Windows Vista], ndis/NdisRetrieveUlong, ndis_memory_ref_929d856f-6798-499a-aa9a-0f5e7181b972.xml, netvista.ndisretrieveulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlRetrieveUlong instead.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisRetrieveUlong
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisRetrieveUlong function
The 
  <b>NdisRetrieveUlong</b> function retrieves a ULONG value from the source address, avoiding alignment
  faults.

## Syntax

````
VOID NdisRetrieveUlong(
  [in] PULONG DestinationAddress,
  [in] PULONG SourceAddress
);
````

## Parameters

`Destination`

TBD

`Source`

TBD


## Return Value

None

## Remarks

The given 
    <i>DestinationAddress</i> is assumed to be aligned on a ULONG boundary.

Callers of 
    <b>NdisRetrieveUlong</b> can be running at any IRQL if the given addresses are in nonpaged pool.
    Otherwise, callers must be running at IRQL &lt; DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlRetrieveUlong instead.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | ndis.h |
| **IRQL** | See Remarks section |

## See Also

<a href="..\ndis\nf-ndis-ndisstoreulong.md">NdisStoreUlong</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRetrieveUlong macro%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>