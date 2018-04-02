---
UID: NS:ndis._NDIS_PROCESSOR_INFO
title: "_NDIS_PROCESSOR_INFO"
author: windows-driver-content
description: The NDIS_PROCESSOR_INFO structure specifies information about a processor in the local computer.
old-location: netvista\ndis_processor_info.htm
old-project: netvista
ms.assetid: 55c7044e-20db-4245-a644-93cbeb9cd512
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_PROCESSOR_INFO, NDIS_PROCESSOR_INFO, NDIS_PROCESSOR_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_PROCESSOR_INFO, PNDIS_PROCESSOR_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROCESSOR_INFO, ndis/NDIS_PROCESSOR_INFO, ndis/PNDIS_PROCESSOR_INFO, ndis_sysinfo_ref_87f00f3b-dc88-4f7d-be9e-39a649aa87a6.xml, netvista.ndis_processor_info"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NDIS_PROCESSOR_INFO_EX.
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
-	NDIS_PROCESSOR_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_PROCESSOR_INFO, *PNDIS_PROCESSOR_INFO
---

# _NDIS_PROCESSOR_INFO structure
The <b>NDIS_PROCESSOR_INFO</b> structure specifies information about a processor in the local
  computer.

## Syntax
```
typedef struct _NDIS_PROCESSOR_INFO {
  ULONG CpuNumber;
  ULONG PhysicalPackageId;
  ULONG CoreId;
  ULONG HyperThreadID;
} NDIS_PROCESSOR_INFO, *PNDIS_PROCESSOR_INFO;
```

## Members


`CpuNumber`

The CPU number that is assigned to the processor. The value is in the range from zero through the
     number of active CPUs minus one.

`PhysicalPackageId`

The physical package ID of the processor. The value is in the range from zero through the number
     in the 
     <b>NumPhysicalPackages</b> member of the 
     <a href="https://msdn.microsoft.com/f59b9394-7742-423d-9a6e-3a429ccb0740">
     NDIS_SYSTEM_PROCESSOR_INFO</a> structure minus one.

`CoreId`

The core ID of the processor. The value is in the range from zero through the number in the 
     <b>NumCoresPerPhysicalPackage</b> member of the NDIS_SYSTEM_PROCESSOR_INFO structure minus one.

`HyperThreadID`

The hyper-threading ID of the processor. The value is in the range from zero through the number in
     the 
     <b>MaxHyperThreadingCpusPerCore</b> member of the NDIS_SYSTEM_PROCESSOR_INFO structure minus one.

## Remarks
The NDIS_PROCESSOR_INFO structure is used in the 
    <a href="https://msdn.microsoft.com/f59b9394-7742-423d-9a6e-3a429ccb0740">
    NDIS_SYSTEM_PROCESSOR_INFO</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NDIS_PROCESSOR_INFO_EX. Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NDIS_PROCESSOR_INFO_EX. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566811">NDIS_PROCESSOR_INFO_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567871">NDIS_SYSTEM_PROCESSOR_INFO</a>