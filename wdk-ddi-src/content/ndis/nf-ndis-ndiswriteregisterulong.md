---
UID: NF:ndis.NdisWriteRegisterUlong
title: NdisWriteRegisterUlong macro
author: windows-driver-content
description: NdisWriteRegisterUlong is called by the miniport driver to write a ULONG to a memory-mapped device register.
old-location: netvista\ndiswriteregisterulong.htm
old-project: netvista
ms.assetid: f21954a8-66a0-40c5-9116-da6e57d24f53
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisWriteRegisterUlong, NdisWriteRegisterUlong macro [Network Drivers Starting with Windows Vista], miniport_register_ref_2f7b1091-df45-47d7-9dd7-9a6f39e0b19d.xml, ndis/NdisWriteRegisterUlong, netvista.ndiswriteregisterulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteRegisterUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteRegisterUlong (NDIS   5.1)) in Windows XP.
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
-	NdisWriteRegisterUlong
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisWriteRegisterUlong function
<b>NdisWriteRegisterUlong</b> is called by the miniport driver to write a ULONG to a memory-mapped device
  register.

## Syntax

````
VOID NdisWriteRegisterUlong(
  [in] PULONG Register,
  [in] ULONG  Data
);
````

## Parameters

`Register`

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>.

`Data`

Specifies the caller-supplied ULONG that this function transfers to the 
     <i>Register</i> .


## Return Value

None

## Remarks

If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteRegisterUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteRegisterUlong (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndiswriteregisteruchar.md">NdisWriteRegisterUchar</a>



<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>



<a href="..\ndis\nf-ndis-ndisreadregisterulong.md">NdisReadRegisterUlong</a>



<a href="..\ndis\nf-ndis-ndiswriteregisterushort.md">NdisWriteRegisterUshort</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>