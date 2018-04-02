---
UID: NF:ndis.NdisStoreUlong
title: NdisStoreUlong macro
author: windows-driver-content
description: The NdisStoreUlong function stores a ULONG value at a particular address, avoiding alignment faults.
old-location: netvista\ndisstoreulong.htm
old-project: netvista
ms.assetid: 4fb0b803-1fe2-409b-8543-dddc5df67fe4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisStoreUlong, NdisStoreUlong macro [Network Drivers Starting with Windows Vista], ndis/NdisStoreUlong, ndis_memory_ref_99349378-c2ab-4f96-82a3-7d76b15aaca3.xml, netvista.ndisstoreulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlStoreUlong instead.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisStoreUlong
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisStoreUlong function
The 
  <b>NdisStoreUlong</b> function stores a ULONG value at a particular address, avoiding alignment
  faults.

## Syntax

```
void NdisStoreUlong(
   Destination,
   Value
);
```

## Parameters

`Destination`

TBD

`Value`

The value to be stored.


## Return Value

None

## Remarks

Callers of 
    <b>NdisStoreUlong</b> can be running at any IRQL if 
    <i>DestinationAddress</i> points to nonpaged pool. Otherwise, the caller must be running at IRQL &lt;
    DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlStoreUlong instead.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | See Remarks section |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564532">NdisRetrieveUlong</a>