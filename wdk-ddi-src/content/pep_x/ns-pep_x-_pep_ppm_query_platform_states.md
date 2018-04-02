---
UID: NS:pep_x._PEP_PPM_QUERY_PLATFORM_STATES
title: "_PEP_PPM_QUERY_PLATFORM_STATES"
author: windows-driver-content
description: The PEP_PPM_QUERY_PLATFORM_STATES structure specifies the number of platform idle states the hardware platform supports.
old-location: kernel\pep_ppm_query_platform_states.htm
old-project: kernel
ms.assetid: 488EC668-15B9-4B6F-B8AA-3142DB87D19B
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_PPM_QUERY_PLATFORM_STATES, PEP_PPM_QUERY_PLATFORM_STATES, PEP_PPM_QUERY_PLATFORM_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_PLATFORM_STATES, PPEP_PPM_QUERY_PLATFORM_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_PLATFORM_STATES, kernel.pep_ppm_query_platform_states, pepfx/PEP_PPM_QUERY_PLATFORM_STATES, pepfx/PPEP_PPM_QUERY_PLATFORM_STATES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
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
-	PEP_PPM_QUERY_PLATFORM_STATES
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_PLATFORM_STATES, *PPEP_PPM_QUERY_PLATFORM_STATES, PEP_PPM_QUERY_PLATFORM_STATES, *PPEP_PPM_QUERY_PLATFORM_STATES
---

# _PEP_PPM_QUERY_PLATFORM_STATES structure
The <b>PEP_PPM_QUERY_PLATFORM_STATES</b> structure specifies the number of platform idle states the hardware platform supports.

## Syntax
```
typedef struct _PEP_PPM_QUERY_PLATFORM_STATES {
  ULONG PlatformStateCount;
} PEP_PPM_QUERY_PLATFORM_STATES, *PPEP_PPM_QUERY_PLATFORM_STATES;
```

## Members


`PlatformStateCount`

The number of platform idle states supported by the platform.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>