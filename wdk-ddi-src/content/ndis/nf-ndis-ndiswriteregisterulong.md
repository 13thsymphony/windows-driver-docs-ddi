---
UID : NF:ndis.NdisWriteRegisterUlong
title : NdisWriteRegisterUlong macro
author : windows-driver-content
description : NdisWriteRegisterUlong is called by the miniport driver to write a ULONG to a memory-mapped device register.
old-location : netvista\ndiswriteregisterulong.htm
old-project : netvista
ms.assetid : f21954a8-66a0-40c5-9116-da6e57d24f53
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NdisWriteRegisterUlong macro [Network Drivers Starting with Windows Vista], netvista.ndiswriteregisterulong, ndis/NdisWriteRegisterUlong, NdisWriteRegisterUlong, miniport_register_ref_2f7b1091-df45-47d7-9dd7-9a6f39e0b19d.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisWriteRegisterUlong (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisWriteRegisterUlong (NDIS   5.1)) in Windows XP.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : ndis.h
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
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
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\ndis\nf-ndis-ndisreadregisterulong.md">NdisReadRegisterUlong</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nf-ndis-ndismmapiospace.md">NdisMMapIoSpace</a>

<a href="..\ndis\nf-ndis-ndiswriteregisterushort.md">NdisWriteRegisterUshort</a>

<a href="..\ndis\nf-ndis-ndiswriteregisteruchar.md">NdisWriteRegisterUchar</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisWriteRegisterUlong macro%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>