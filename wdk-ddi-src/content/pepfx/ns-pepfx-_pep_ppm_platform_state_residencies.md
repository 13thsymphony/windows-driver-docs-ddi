---
UID: NS:pepfx._PEP_PPM_PLATFORM_STATE_RESIDENCIES
title: "_PEP_PPM_PLATFORM_STATE_RESIDENCIES"
author: windows-driver-content
description: The PEP_PPM_PLATFORM_STATE_RESIDENCIES structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform.
old-location: kernel\pep_ppm_platform_state_residencies.htm
old-project: kernel
ms.assetid: 5B6186EB-EC08-4C11-9CCF-E07D78FBD535
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_PPM_PLATFORM_STATE_RESIDENCIES, PEP_PPM_PLATFORM_STATE_RESIDENCIES, PEP_PPM_PLATFORM_STATE_RESIDENCIES structure [Kernel-Mode Driver Architecture], PPEP_PPM_PLATFORM_STATE_RESIDENCIES, PPEP_PPM_PLATFORM_STATE_RESIDENCIES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_PLATFORM_STATE_RESIDENCIES, kernel.pep_ppm_platform_state_residencies, pepfx/PEP_PPM_PLATFORM_STATE_RESIDENCIES, pepfx/PPEP_PPM_PLATFORM_STATE_RESIDENCIES"
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
-	PEP_PPM_PLATFORM_STATE_RESIDENCIES
product: Windows
targetos: Windows
req.typenames: PEP_PPM_PLATFORM_STATE_RESIDENCIES, *PPEP_PPM_PLATFORM_STATE_RESIDENCIES
---

# _PEP_PPM_PLATFORM_STATE_RESIDENCIES structure
The <b>PEP_PPM_PLATFORM_STATE_RESIDENCIES</b> structure contains the accumulated residency times and transition counts for the idle states that are supported by the hardware platform.

## Syntax
````
typedef struct _PEP_PPM_PLATFORM_STATE_RESIDENCIES {
  ULONG                             Count;
  PPEP_PPM_PLATFORM_STATE_RESIDENCY States;
} PEP_PPM_PLATFORM_STATE_RESIDENCIES, *PPEP_PPM_PLATFORM_STATE_RESIDENCIES;
````

## Members


`Count`

[in] The number of elements in the array pointed to by the <b>States</b> member. The number of array elements equals the number of platform idle states that the PEP previously provided in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification.

`States`

[in] A pointer to an output buffer to which the PEP writes an array of <a href="..\pepfx\ns-pepfx-_pep_ppm_platform_state_residency.md">PEP_PPM_PLATFORM_STATE_RESIDENCY</a> structures. Each structure contains the accumulated residency and transition count information for a particular platform idle state. This buffer is guaranteed to be large enough to contain the number of array elements specified by the <b>Count</b> member. Each idle state is identified by its array index. If the array contains N elements, idle state indexes range from 0 to N-1.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186817">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE_RESIDENCIES</a> notification. Both members of the structure contain input values that the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) supplies when this notification is sent to the PEP. PoFx allocates the output buffer pointed to by the <b>States</b> member, and the PEP writes to this buffer.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186817">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE_RESIDENCIES</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>



<a href="..\pepfx\ns-pepfx-_pep_ppm_platform_state_residency.md">PEP_PPM_PLATFORM_STATE_RESIDENCY</a>