---
UID: NF:ndis.NdisReadRegisterUshort
title: NdisReadRegisterUshort macro
author: windows-driver-content
description: NdisReadRegisterUshort is called by the miniport driver to read a USHORT from a memory-mapped device register.
old-location: netvista\ndisreadregisterushort.htm
old-project: netvista
ms.assetid: 0048fb18-8728-4b41-b4e2-5762966d5ed0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisReadRegisterUshort, NdisReadRegisterUshort macro [Network Drivers Starting with Windows Vista], miniport_register_ref_7eef891a-3f3e-4c42-8165-399555eb018f.xml, ndis/NdisReadRegisterUshort, netvista.ndisreadregisterushort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadRegisterUshort (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadRegisterUshort (NDIS   5.1)) in Windows XP.
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
-	NdisReadRegisterUshort
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisReadRegisterUshort function
<b>NdisReadRegisterUshort</b> is called by the miniport driver to read a USHORT from a memory-mapped device
  register.

## Syntax

````
VOID NdisReadRegisterUshort(
  [in]  PUSHORT Register,
  [out] PUSHORT Data
);
````

## Parameters

`Register`

Pointer to the memory-mapped register. This virtual address must fall within a range returned by
     an initialization-time call to 
     <a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>.

`Data`

Pointer to the caller-supplied variable in which this function returns the USHORT read from 
     <i>Register</i> .


## Return Value

None

## Remarks

If a driver calls this function, a NIC's device registers must be mapped to noncached memory during
    driver initialization.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisReadRegisterUshort (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisReadRegisterUshort (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | Any level |

## See Also

<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>



<a href="..\ndis\nf-ndis-ndisreadregisterulong.md">NdisReadRegisterUlong</a>



<a href="..\ndis\nf-ndis-ndiswriteregisterushort.md">NdisWriteRegisterUshort</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndisreadregisteruchar.md">NdisReadRegisterUchar</a>