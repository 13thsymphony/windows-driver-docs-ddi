---
UID: NS:ntddndis._NDIS_PROCESSOR_INFO_EX
title: "_NDIS_PROCESSOR_INFO_EX"
author: windows-driver-content
description: The NDIS_PROCESSOR_INFO_EX structure specifies information about a processor in the local computer.
old-location: netvista\ndis_processor_info_ex.htm
old-project: netvista
ms.assetid: e4f28f30-32bc-4bbc-8e95-f87dfe80229d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_PROCESSOR_INFO_EX, NDIS_PROCESSOR_INFO_EX, NDIS_PROCESSOR_INFO_EX structure [Network Drivers Starting with Windows Vista], PNDIS_PROCESSOR_INFO_EX, PNDIS_PROCESSOR_INFO_EX structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROCESSOR_INFO_EX, ndis_processor_group_ref_0a75adfb-c28f-4d9b-8b29-6da14662bda7.xml, netvista.ndis_processor_info_ex, ntddndis/NDIS_PROCESSOR_INFO_EX, ntddndis/PNDIS_PROCESSOR_INFO_EX"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_PROCESSOR_INFO_EX
product: Windows
targetos: Windows
req.typenames: NDIS_PROCESSOR_INFO_EX, *PNDIS_PROCESSOR_INFO_EX
---

# _NDIS_PROCESSOR_INFO_EX structure
The <b>NDIS_PROCESSOR_INFO_EX</b> structure specifies information about a processor in the local
  computer.

## Syntax
````
typedef struct _NDIS_PROCESSOR_INFO_EX {
  PROCESSOR_NUMBER ProcNum;
  ULONG            SocketId;
  ULONG            CoreId;
  ULONG            HyperThreadId;
  USHORT           NodeId;
  USHORT           NodeDistance;
} NDIS_PROCESSOR_INFO_EX, *PNDIS_PROCESSOR_INFO_EX;
````

## Members


`CoreId`

The core ID of the processor. The value is in the range from zero through the number in the 
     <b>NumCoresPerSocket</b> member of the NDIS_SYSTEM_PROCESSOR_INFO_EX structure minus one.

`HyperThreadId`

The hyper-threading ID of the processor. The value is in the range from zero through the number in
     the 
     <b>MaxHyperThreadingProcsPerCore</b> member of the NDIS_SYSTEM_PROCESSOR_INFO_EX structure minus
     one.

`NodeDistance`

The node distance of the processor. If the handle at the 
     <i>NdisHandle</i> parameter that the caller passed to the 
     <a href="..\ndis\nf-ndis-ndisgetprocessorinformationex.md">
     NdisGetProcessorInformationEx</a> function is not <b>NULL</b> and is a miniport adapter handle, this member
     contains the distance of the corresponding NIC from this processor's NUMA node. Otherwise, this member
     is zero for miniport drivers or USHORT_MAX (0xffff) for other drivers.

`NodeId`

The node identifier of the processor. This is the number of the NUMA node to which the processor
     belongs. This range of possible values is zero to the number of NUMA nodes on the local computer minus
     one.

`ProcNum`

The processor number that is assigned to the processor.

`SocketId`

The socket identifier for the processor. This is the number that is assigned to the motherboard
     socket on the local computer. That is, it is a physical processor identifier. The possible values for
     this member are zero to the number of sockets on the motherboard minus one.

## Remarks
The NDIS_PROCESSOR_INFO_EX structure is used in the 
    <a href="..\ntddndis\ns-ntddndis-_ndis_system_processor_info_ex.md">
    NDIS_SYSTEM_PROCESSOR_INFO_EX</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_system_processor_info_ex.md">NDIS_SYSTEM_PROCESSOR_INFO_EX</a>



<a href="..\ndis\nf-ndis-ndisgetprocessorinformationex.md">
   NdisGetProcessorInformationEx</a>



<a href="..\ndis\ns-ndis-_ndis_processor_info.md">NDIS_PROCESSOR_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROCESSOR_INFO_EX structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>