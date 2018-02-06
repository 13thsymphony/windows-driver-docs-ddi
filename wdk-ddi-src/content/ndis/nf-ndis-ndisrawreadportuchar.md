---
UID: NF:ndis.NdisRawReadPortUchar
title: NdisRawReadPortUchar macro
author: windows-driver-content
description: NdisRawReadPortUchar reads a byte from a given I/O port on the NIC.
old-location: netvista\ndisrawreadportuchar.htm
old-project: netvista
ms.assetid: 5bda6d10-dd68-4385-b71c-8319e6ed0d4a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisrawreadportuchar, ndis/NdisRawReadPortUchar, NdisRawReadPortUchar macro [Network Drivers Starting with Windows Vista], NdisRawReadPortUchar, miniport_port_raw_ref_e478dfdb-7037-4a9e-8da5-3bc38561094f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortUchar (NDIS   5.1)) in Windows XP.
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
-	NdisRawReadPortUchar
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisRawReadPortUchar function
<b>NdisRawReadPortUchar</b> reads a byte from a given I/O port on the NIC.

## Syntax

````
VOID NdisRawReadPortUchar(
  [in]  ULONG_PTR Port,
  [out] PUCHAR    Data
);
````

## Parameters

`Port`

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.

`Data`

Pointer to a caller-supplied variable in which this function returns a byte read in from the
     port.


## Return Value

None

## Remarks

<b>NdisRawReadPortUchar</b> runs fast
    because it need not map a bus-relative I/O port address onto a host-dependent logical port address at
    every call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortUchar (NDIS   5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortUchar (NDIS   5.1)) in Windows XP. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | ndis.h |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>

<a href="..\ndis\nf-ndis-ndisrawreadportbufferuchar.md">NdisRawReadPortBufferUchar</a>

<a href="..\ndis\nf-ndis-ndisrawreadportulong.md">NdisRawReadPortUlong</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisrawwriteportuchar.md">NdisRawWritePortUchar</a>

<a href="..\ndis\nf-ndis-ndisrawreadportushort.md">NdisRawReadPortUshort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRawReadPortUchar macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>