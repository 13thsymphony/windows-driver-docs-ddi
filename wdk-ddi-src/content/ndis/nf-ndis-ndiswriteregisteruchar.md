---
UID: NF:ndis.NdisWriteRegisterUchar
title: NdisWriteRegisterUchar macro
author: windows-driver-content
description: NdisWriteRegisterUchar is called by the miniport driver to write a UCHAR to a memory-mapped device register.
old-location: netvista\ndiswriteregisteruchar.htm
old-project: netvista
ms.assetid: 8f720af6-d70a-4682-86f4-011e70a6f64f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisWriteRegisterUchar, NdisWriteRegisterUchar macro [Network Drivers Starting with Windows Vista], miniport_register_ref_60f684ba-a2ca-4fa8-8a80-9e805fb5c453.xml, ndis/NdisWriteRegisterUchar, netvista.ndiswriteregisteruchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteRegisterUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteRegisterUchar (NDIS   5.1)) in Windows XP.
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
-	NdisWriteRegisterUchar
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisWriteRegisterUchar function
<b>NdisWriteRegisterUchar</b> is called by the miniport driver to write a UCHAR to a memory-mapped device
  register.

## Syntax

````
VOID NdisWriteRegisterUchar(
  [in] PUCHAR Register,
  [in] UCHAR  Data
);
````

## Parameters

`Register`

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>.

`Data`

Specifies the caller-supplied UCHAR that this function transfers to the 
     <i>Register</i> .


## Return Value

None

## Remarks

If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteRegisterUchar (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteRegisterUchar (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>



<a href="..\ndis\nf-ndis-ndiswriteregisterulong.md">NdisWriteRegisterUlong</a>



<a href="..\ndis\nf-ndis-ndiswriteregisterushort.md">NdisWriteRegisterUshort</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisreadregisteruchar.md">NdisReadRegisterUchar</a>