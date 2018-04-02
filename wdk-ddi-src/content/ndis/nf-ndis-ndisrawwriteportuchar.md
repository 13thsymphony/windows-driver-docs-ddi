---
UID: NF:ndis.NdisRawWritePortUchar
title: NdisRawWritePortUchar macro
author: windows-driver-content
description: NdisRawWritePortUchar writes a byte to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportuchar.htm
old-project: netvista
ms.assetid: 9fcbf570-d272-4373-86ca-8466fb5fc18c
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisRawWritePortUchar, NdisRawWritePortUchar macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_00cc5f8f-4965-4cc3-bdc6-25dcf2128582.xml, ndis/NdisRawWritePortUchar, netvista.ndisrawwriteportuchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortUchar (NDIS   5.1)) in Windows XP.
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
-	NdisRawWritePortUchar
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisRawWritePortUchar function
<b>NdisRawWritePortUchar</b> writes a byte to an I/O port on the NIC.

## Syntax

```
void NdisRawWritePortUchar(
   Port,
   Data
);
```

## Parameters

`Port`

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="https://msdn.microsoft.com/3e7fc02b-9562-44b9-8659-793a1d96d1e9">
     NdisMRegisterIoPortRange</a>.

`Data`

Specifies the byte to be written.


## Return Value

None

## Remarks

<b>NdisRawWritePortUchar</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortUchar (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh975121">NdisMRegisterIoPortRange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563794">NdisRawReadPortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563811">NdisRawWritePortBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563832">NdisRawWritePortUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564510">NdisRawWritePortUshort</a>