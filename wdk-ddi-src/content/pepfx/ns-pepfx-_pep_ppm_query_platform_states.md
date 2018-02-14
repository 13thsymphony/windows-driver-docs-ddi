---
UID: NS:pepfx._PEP_PPM_QUERY_PLATFORM_STATES
title: "_PEP_PPM_QUERY_PLATFORM_STATES"
author: windows-driver-content
description: The PEP_PPM_QUERY_PLATFORM_STATES structure specifies the number of platform idle states the hardware platform supports.
old-location: kernel\pep_ppm_query_platform_states.htm
old-project: kernel
ms.assetid: 488EC668-15B9-4B6F-B8AA-3142DB87D19B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: "_PEP_PPM_QUERY_PLATFORM_STATES, *PPEP_PPM_QUERY_PLATFORM_STATES, PPEP_PPM_QUERY_PLATFORM_STATES structure pointer [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_PLATFORM_STATES, pepfx/PPEP_PPM_QUERY_PLATFORM_STATES, pepfx/PEP_PPM_QUERY_PLATFORM_STATES, PEP_PPM_QUERY_PLATFORM_STATES structure [Kernel-Mode Driver Architecture], kernel.pep_ppm_query_platform_states, PEP_PPM_QUERY_PLATFORM_STATES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PPM_QUERY_PLATFORM_STATES
product: Windows
targetos: Windows
req.typenames: "*PPEP_PPM_QUERY_PLATFORM_STATES, PEP_PPM_QUERY_PLATFORM_STATES"
---

# _PEP_PPM_QUERY_PLATFORM_STATES structure
The <b>PEP_PPM_QUERY_PLATFORM_STATES</b> structure specifies the number of platform idle states the hardware platform supports.

## Syntax
````
typedef struct _PEP_PPM_QUERY_PLATFORM_STATES {
  ULONG PlatformStateCount;
} PEP_PPM_QUERY_PLATFORM_STATES, *PPEP_PPM_QUERY_PLATFORM_STATES;
````

## Members


`PlatformStateCount`

The number of platform idle states supported by the platform.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_PLATFORM_STATES structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>