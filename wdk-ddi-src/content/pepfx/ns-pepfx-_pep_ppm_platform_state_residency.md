---
UID: NS:pepfx._PEP_PPM_PLATFORM_STATE_RESIDENCY
title: "_PEP_PPM_PLATFORM_STATE_RESIDENCY"
author: windows-driver-content
description: The PEP_PPM_PLATFORM_STATE_RESIDENCY structure specifies the accumulated residency time and transition count for a particular platform idle state.
old-location: kernel\pep_ppm_platform_state_residency.htm
old-project: kernel
ms.assetid: 35DB4043-F1B6-43C0-B8E7-FCEFF1E7E459
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_PPM_PLATFORM_STATE_RESIDENCY, PEP_PPM_PLATFORM_STATE_RESIDENCY, PEP_PPM_PLATFORM_STATE_RESIDENCY structure [Kernel-Mode Driver Architecture], PPEP_PPM_PLATFORM_STATE_RESIDENCY, PPEP_PPM_PLATFORM_STATE_RESIDENCY structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PLATFORM_STATE_RESIDENCY, kernel.pep_ppm_platform_state_residency, pepfx/PEP_PPM_PLATFORM_STATE_RESIDENCY, pepfx/PPEP_PPM_PLATFORM_STATE_RESIDENCY"
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
-	PEP_PPM_PLATFORM_STATE_RESIDENCY
product: Windows
targetos: Windows
req.typenames: PEP_PPM_PLATFORM_STATE_RESIDENCY, *PPEP_PPM_PLATFORM_STATE_RESIDENCY
---

# _PEP_PPM_PLATFORM_STATE_RESIDENCY structure
The <b>PEP_PPM_PLATFORM_STATE_RESIDENCY</b> structure specifies the accumulated residency time and transition count for a particular platform idle state.

## Syntax
````
typedef struct _PEP_PPM_PLATFORM_STATE_RESIDENCY {
  ULONG64 Residency;
  ULONG64 TransitionCount;
} PEP_PPM_PLATFORM_STATE_RESIDENCY, *PPEP_PPM_PLATFORM_STATE_RESIDENCY;
````

## Members


`Residency`

The accumulated residency time, in 100-nanosecond units. This is the total amount of time that the hardware platform has spent in this idle state since system startup.

`TransitionCount`

The total number of times that the platform has entered this idle state since system startup.

## Remarks
The <b>States</b> member of the <a href="..\pepfx\ns-pepfx-_pep_ppm_platform_state_residencies.md">PEP_PPM_PLATFORM_STATE_RESIDENCIES</a> structure is a pointer to an array of <b>PEP_PPM_PLATFORM_STATE_RESIDENCY</b> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="..\pepfx\ns-pepfx-_pep_ppm_platform_state_residencies.md">PEP_PPM_PLATFORM_STATE_RESIDENCIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_PLATFORM_STATE_RESIDENCY structure%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>