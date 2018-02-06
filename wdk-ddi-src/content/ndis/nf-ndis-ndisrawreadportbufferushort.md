---
UID: NF:ndis.NdisRawReadPortBufferUshort
title: NdisRawReadPortBufferUshort macro
author: windows-driver-content
description: NdisRawReadPortBufferUshort reads a specified number of USHORTs into a caller-supplied buffer.
old-location: netvista\ndisrawreadportbufferushort.htm
old-project: netvista
ms.assetid: c100aad1-2fb9-49e0-b68e-20b165a69701
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisrawreadportbufferushort, ndis/NdisRawReadPortBufferUshort, miniport_port_raw_ref_fc8d7120-4fbc-46e3-9946-c269f2992f56.xml, NdisRawReadPortBufferUshort, NdisRawReadPortBufferUshort macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortBufferUshort   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortBufferUshort   (NDIS 5.1)) in Windows XP.
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
-	NdisRawReadPortBufferUshort
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisRawReadPortBufferUshort function
<b>NdisRawReadPortBufferUshort</b> reads a specified number of USHORTs into a caller-supplied buffer.

## Syntax

````
VOID NdisRawReadPortBufferUshort(
  [in]  ULONG_PTR Port,
  [out] PUSHORT   Buffer,
  [in]  ULONG     Length
);
````

## Parameters

`Port`

Specifies the I/O port. This address falls in a range that was mapped during initialization with 
     <a href="..\ndis\nf-ndis-ndismregisterioportrange.md">
     NdisMRegisterIoPortRange</a>.

`Buffer`

Pointer to a caller-allocated buffer, in resident memory, into which the USHORTs will be
     transferred from the NIC. The caller must allocate a buffer at least (<b>sizeof</b>(USHORT)
     *
     <i>Length</i> ).

`Length`

Specifies how many USHORTs to transfer from the NIC.


## Return Value

None

## Remarks

<b>NdisRawReadPortBufferUshort</b> reads each USHORT value, one at a time, from the given I/O port into
    the given buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortBufferUshort   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortBufferUshort   (NDIS 5.1)) in Windows XP. Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisRawReadPortBufferUshort   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisRawReadPortBufferUshort   (NDIS 5.1)) in Windows XP. |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | ndis.h |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndisrawreadportbufferulong.md">NdisRawReadPortBufferUlong</a>

<a href="..\ndis\nf-ndis-ndisrawreadportbufferuchar.md">NdisRawReadPortBufferUchar</a>

<a href="..\ndis\nf-ndis-ndisrawreadportushort.md">NdisRawReadPortUshort</a>

<a href="..\ndis\nf-ndis-ndismregisterioportrange.md">NdisMRegisterIoPortRange</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndisrawwriteportbufferushort.md">NdisRawWritePortBufferUshort</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisRawReadPortBufferUshort macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>