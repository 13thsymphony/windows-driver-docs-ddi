---
UID : NS:ndis._NDIS_PROCESSOR_INFO
title : "_NDIS_PROCESSOR_INFO"
author : windows-driver-content
description : The NDIS_PROCESSOR_INFO structure specifies information about a processor in the local computer.
old-location : netvista\ndis_processor_info.htm
old-project : netvista
ms.assetid : 55c7044e-20db-4245-a644-93cbeb9cd512
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis/PNDIS_PROCESSOR_INFO, *PNDIS_PROCESSOR_INFO, _NDIS_PROCESSOR_INFO, NDIS_PROCESSOR_INFO, PNDIS_PROCESSOR_INFO, PNDIS_PROCESSOR_INFO structure pointer [Network Drivers Starting with Windows Vista], netvista.ndis_processor_info, ndis_sysinfo_ref_87f00f3b-dc88-4f7d-be9e-39a649aa87a6.xml, ndis/NDIS_PROCESSOR_INFO, NDIS_PROCESSOR_INFO structure [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.0 and 6.1. For NDIS 6.20 and later, use NDIS_PROCESSOR_INFO_EX.
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
req.lib : 
req.dll : 
req.irql : See Remarks section
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PNDIS_PROCESSOR_INFO, NDIS_PROCESSOR_INFO"
---

# _NDIS_PROCESSOR_INFO structure
The <b>NDIS_PROCESSOR_INFO</b> structure specifies information about a processor in the local
  computer.

## Syntax
````
typedef struct _NDIS_PROCESSOR_INFO {
  ULONG CpuNumber;
  ULONG PhysicalPackageId;
  ULONG CoreId;
  ULONG HyperThreadID;
} NDIS_PROCESSOR_INFO, *PNDIS_PROCESSOR_INFO;
````

## Members


`CoreId`

The core ID of the processor. The value is in the range from zero through the number in the 
     <b>NumCoresPerPhysicalPackage</b> member of the NDIS_SYSTEM_PROCESSOR_INFO structure minus one.

`CpuNumber`

The CPU number that is assigned to the processor. The value is in the range from zero through the
     number of active CPUs minus one.

`HyperThreadID`

The hyper-threading ID of the processor. The value is in the range from zero through the number in
     the 
     <b>MaxHyperThreadingCpusPerCore</b> member of the NDIS_SYSTEM_PROCESSOR_INFO structure minus one.

`PhysicalPackageId`

The physical package ID of the processor. The value is in the range from zero through the number
     in the 
     <b>NumPhysicalPackages</b> member of the 
     <mshelp:link keywords="netvista.ndis_system_processor_info" tabindex="0"><b>
     NDIS_SYSTEM_PROCESSOR_INFO</b></mshelp:link> structure minus one.

## Remarks
The NDIS_PROCESSOR_INFO structure is used in the 
    <mshelp:link keywords="netvista.ndis_system_processor_info" tabindex="0"><b>
    NDIS_SYSTEM_PROCESSOR_INFO</b></mshelp:link> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="..\ndis\ns-ndis-_ndis_system_processor_info.md">NDIS_SYSTEM_PROCESSOR_INFO</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_processor_info_ex.md">NDIS_PROCESSOR_INFO_EX</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PROCESSOR_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>