---
UID : NS:storport._MEMORY_REGION
title : _MEMORY_REGION
author : windows-driver-content
description : The MEMORY_REGION structure describes a region of physically contiguous memory.
old-location : storage\memory_region.htm
old-project : storage
ms.assetid : b8dbc3d4-7a70-4ec6-b7b0-2b0877fb9722
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : PMEMORY_REGION, structs-storport_4ed10515-f1ce-4767-bbdc-239ac00a5cbe.xml, storport/MEMORY_REGION, *PMEMORY_REGION, MEMORY_REGION structure [Storage Devices], storport/PMEMORY_REGION, PMEMORY_REGION structure pointer [Storage Devices], storage.memory_region, _MEMORY_REGION, MEMORY_REGION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : storport.h
req.include-header : Storport.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : MEMORY_REGION, *PMEMORY_REGION
req.product : Windows 10 or later.
---

# _MEMORY_REGION structure
The MEMORY_REGION structure describes a region of physically contiguous memory.

## Syntax
````
typedef struct _MEMORY_REGION {
  PUCHAR           VirtualBase;
  PHYSICAL_ADDRESS PhysicalBase;
  ULONG            Length;
} MEMORY_REGION, *PMEMORY_REGION;
````

## Members


`Length`

The size, in bytes, of the memory region.

`PhysicalBase`

The beginning physical address of the memory region.

`VirtualBase`

The beginning virtual address of the memory region.

## Remarks
The <b>DumpRegion</b> member of the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structure holds a MEMORY_REGION structure that describes a region of physically contiguous memory that a miniport driver can use during a crash dump.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | storport.h (include Storport.h) |

## See Also

<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MEMORY_REGION structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>