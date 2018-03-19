---
UID: NF:ndis.NdisRawWritePortUlong
title: NdisRawWritePortUlong macro
author: windows-driver-content
description: NdisRawWritePortUlong writes a ULONG value to an I/O port on the NIC.
old-location: netvista\ndisrawwriteportulong.htm
old-project: netvista
ms.assetid: 24abe892-7d49-4bc4-8862-e375f9862a5f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisRawWritePortUlong, NdisRawWritePortUlong macro [Network Drivers Starting with Windows Vista], miniport_port_raw_ref_54b23b9a-fb43-4591-a123-6c564850f5cf.xml, ndis/NdisRawWritePortUlong, netvista.ndisrawwriteportulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortUlong (NDIS   5.1)) in Windows XP.
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
-	NdisRawWritePortUlong
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisRawWritePortUlong function
<b>NdisRawWritePortUlong</b> writes a ULONG value to an I/O port on the NIC.

## Syntax

````
VOID NdisRawWritePortUlong(
  [in] ULONG_PTR Port,
  [in] ULONG     Data
);
````

## Parameters

`Port`

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.

`Data`

Specifies the ULONG to be written.


## Return Value

None

## Remarks

<b>NdisRawWritePortUlong</b> runs fast because it need not map a bus-relative I/O port address onto a
    host-dependent logical port address at every call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawWritePortUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawWritePortUlong (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndisrawwriteportbufferulong.md">NdisRawWritePortBufferUlong</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportushort.md">NdisRawWritePortUshort</a>



<a href="..\ndis\nf-ndis-ndisrawreadportulong.md">NdisRawReadPortUlong</a>



<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisrawwriteportuchar.md">NdisRawWritePortUchar</a>