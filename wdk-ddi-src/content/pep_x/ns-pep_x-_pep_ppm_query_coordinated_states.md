---
UID: NS:pep_x._PEP_PPM_QUERY_COORDINATED_STATES
title: "_PEP_PPM_QUERY_COORDINATED_STATES"
author: windows-driver-content
description: The PEP_PPM_QUERY_COORDINATED_STATES structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports.
old-location: kernel\pep_ppm_query_coordinated_states.htm
old-project: kernel
ms.assetid: 9C7E41E8-AFB4-4421-8773-EBDA5F779364
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_PPM_QUERY_COORDINATED_STATES, *PPEP_PPM_QUERY_IDLE_STATES_V2, PEP_PPM_QUERY_COORDINATED_STATES, PEP_PPM_QUERY_COORDINATED_STATES structure [Kernel-Mode Driver Architecture], PEP_PPM_QUERY_IDLE_STATES_V2, PPEP_PPM_QUERY_COORDINATED_STATES, PPEP_PPM_QUERY_COORDINATED_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_COORDINATED_STATES, kernel.pep_ppm_query_coordinated_states, pepfx/PEP_PPM_QUERY_COORDINATED_STATES, pepfx/PPEP_PPM_QUERY_COORDINATED_STATES"
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
-	PEP_PPM_QUERY_COORDINATED_STATES
product: Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_COORDINATED_STATES, *PPEP_PPM_QUERY_COORDINATED_STATES, PEP_PPM_QUERY_COORDINATED_STATES, *PPEP_PPM_QUERY_COORDINATED_STATES, PEP_PPM_QUERY_IDLE_STATES_V2, *PPEP_PPM_QUERY_IDLE_STATES_V2
---

# _PEP_PPM_QUERY_COORDINATED_STATES structure
The <b>PEP_PPM_QUERY_COORDINATED_STATES</b> structure contains information about each coordinated idle state that the platform extension plug-in (PEP) supports.

## Syntax
````
typedef struct _PEP_PPM_QUERY_COORDINATED_STATES {
  ULONG                                          Count;
  _Field_size_(Count) PEP_COORDINATED_IDLE_STATE States[ANYSIZE_ARRAY];
} PEP_PPM_QUERY_COORDINATED_STATES, *PPEP_PPM_QUERY_COORDINATED_STATES;
````

## Members


`Count`

[in] The size of the <b>States</b> array. This will be equal to the <b>PlatformStateCount</b> returned from the query platform states notification.

`States`

[out] An array of <a href="..\pepfx\ns-pepfx-_pep_coordinated_idle_state.md">PEP_COORDINATED_IDLE_STATE</a> structures that contains information about each coordinated idle state that the PEP supports.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES notification</a>



<a href="..\pepfx\ns-pepfx-_pep_coordinated_idle_state.md">PEP_COORDINATED_IDLE_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186776">PEP_NOTIFY_PPM_QUERY_COORDINATED_STATES notification</a>