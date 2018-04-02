---
UID: NS:pepfx._PEP_PPM_QUERY_PLATFORM_STATE
title: "_PEP_PPM_QUERY_PLATFORM_STATE"
author: windows-driver-content
description: The PEP_PPM_QUERY_PLATFORM_STATE structure contains information about a platform idle state.
old-location: kernel\pep_ppm_query_platform_state.htm
old-project: kernel
ms.assetid: 767F7364-07E4-4B64-AEAE-EEAEEADA5DFE
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_PPM_QUERY_PLATFORM_STATE, PEP_PPM_QUERY_PLATFORM_STATE, PEP_PPM_QUERY_PLATFORM_STATE structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_PLATFORM_STATE, PPEP_PPM_QUERY_PLATFORM_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_PLATFORM_STATE, kernel.pep_ppm_query_platform_state, pepfx/PEP_PPM_QUERY_PLATFORM_STATE, pepfx/PPEP_PPM_QUERY_PLATFORM_STATE"
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
-	PEP_PPM_QUERY_PLATFORM_STATE
product: Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_PLATFORM_STATE, *PPEP_PPM_QUERY_PLATFORM_STATE
---

# _PEP_PPM_QUERY_PLATFORM_STATE structure
The <b>PEP_PPM_QUERY_PLATFORM_STATE</b> structure contains information about a platform idle state.

## Syntax
```
typedef struct _PEP_PPM_QUERY_PLATFORM_STATE {
  ULONG                   StateIndex;
  PEP_PLATFORM_IDLE_STATE State;
} *PPEP_PPM_QUERY_PLATFORM_STATE, PEP_PPM_QUERY_PLATFORM_STATE;
```

## Members


`StateIndex`

[in] The index of this platform idle state. If the hardware platform supports N platform idle states, the states are numbered 0 to N-1. The Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) previously sent a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification to the platform extension plug-in (PEP) to determine the number of supported platform idle states.

`State`

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/mt186794">PEP_PLATFORM_IDLE_STATE</a> structure that describes the platform idle state.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notification. The <b>StateIndex</b> member of the <b>PEP_PPM_QUERY_PLATFORM_STATE</b> structure contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent to the PEP. The <b>State</b> member contains an output value that the PEP writes to the structure in response to the notification.

The buffer that PoFx allocates to hold the <b>PEP_PPM_QUERY_PLATFORM_STATE</b> structure is guaranteed to be large enough to contain this structure plus any elements of the <b>State.DependencyArray</b> array that follow this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pepfx.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186794">PEP_PLATFORM_IDLE_STATE</a>