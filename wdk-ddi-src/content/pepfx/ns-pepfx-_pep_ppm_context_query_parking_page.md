---
UID: NS:pepfx._PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
title: "_PEP_PPM_CONTEXT_QUERY_PARKING_PAGE"
author: windows-driver-content
description: The PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure describes the parking page for a processor.
old-location: kernel\pep_ppm_context_query_parking_page.htm
old-project: kernel
ms.assetid: F714D6EE-90F9-4FC6-95EB-32225284DC1F
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE, PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure [Kernel-Mode Driver Architecture], PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE, PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, kernel.pep_ppm_context_query_parking_page, pepfx/PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, pepfx/PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
-	pepfx.h
api_name:
-	PEP_PPM_CONTEXT_QUERY_PARKING_PAGE
product: Windows
targetos: Windows
req.typenames: PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, *PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE
---

# _PEP_PPM_CONTEXT_QUERY_PARKING_PAGE structure
The <b>PEP_PPM_CONTEXT_QUERY_PARKING_PAGE</b> structure describes the parking page for a processor.

## Syntax
````
typedef struct _PEP_PPM_CONTEXT_QUERY_PARKING_PAGE {
  PHYSICAL_ADDRESS PhysicalPageAddress;
  PVOID            VirtualPageAddress;
} PEP_PPM_CONTEXT_QUERY_PARKING_PAGE, *PPEP_PPM_CONTEXT_QUERY_PARKING_PAGE;
````

## Members


`PhysicalPageAddress`

The physical memory address of the parking page.

`VirtualPageAddress`

The virtual memory address of the parking page.

## Remarks
The output buffer for a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186798">PEP_PPM_POWER_CONTROL_QUERY_PARKING_PAGE</a> power control request is a <b>PEP_PPM_CONTEXT_QUERY_PARKING_PAGE</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186798">PEP_PPM_POWER_CONTROL_QUERY_PARKING_PAGE</a>