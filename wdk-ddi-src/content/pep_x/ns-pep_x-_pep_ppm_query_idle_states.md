---
UID: NS:pep_x._PEP_PPM_QUERY_IDLE_STATES
title: "_PEP_PPM_QUERY_IDLE_STATES"
author: windows-driver-content
description: The PEP_PPM_QUERY_IDLE_STATES structure describes the idle states of a particular processor.
old-location: kernel\pep_ppm_query_idle_states.htm
old-project: kernel
ms.assetid: 27B43684-6564-41A0-9F0D-D49F88D1F14D
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PPEP_PPM_QUERY_IDLE_STATES, PEP_PPM_QUERY_IDLE_STATES, PEP_PPM_QUERY_IDLE_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_IDLE_STATES, PPEP_PPM_QUERY_IDLE_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_IDLE_STATES, kernel.pep_ppm_query_idle_states, pep_x/PEP_PPM_QUERY_IDLE_STATES, pep_x/PPEP_PPM_QUERY_IDLE_STATES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pepfx.h
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
-	pep_x.h
api_name:
-	PEP_PPM_QUERY_IDLE_STATES
product: Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_IDLE_STATES, *PPEP_PPM_QUERY_IDLE_STATES
---

# _PEP_PPM_QUERY_IDLE_STATES structure
The <b>PEP_PPM_QUERY_IDLE_STATES</b> structure describes the idle states of a particular processor.

## Syntax
````
typedef struct _PEP_PPM_QUERY_IDLE_STATES {
  ULONG                    Count;
  ULONG                    MaximumCoordinatedProcessors;
  PEP_PROCESSOR_IDLE_STATE IdleStates[ANYSIZE_ARRAY];
} PEP_PPM_QUERY_IDLE_STATES, *PPEP_PPM_QUERY_IDLE_STATES;
````

## Members


`Count`

[in] The number of elements in the <b>IdleStates</b> array. This member is set to the <b>IdleStateCount</b> value that the PEP previously supplied for this processor in response to the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186820">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a> notification.

`MaximumCoordinatedProcessors`

[out] The maximum number of secondary processors that are subordinate to this processor for any transitions to idle states. A primary processor can enter the selected idle state only after the secondary processors have entered their corresponding idle states. The PEP must set the <b>MaximumCoordinatedProcessors</b> member to a number that is less than the total number of processors in the hardware platform.

`IdleStates`

[in] The first element in an array of <a href="..\pep_x\ns-pep_x-_pep_processor_idle_state.md">PEP_PROCESSOR_IDLE_STATE</a> structures. Each array element describes one of the idle states of this processor. If the array contains more than one element, the additional elements immediately follow the end of the <b>PEP_PPM_QUERY_IDLE_STATES</b> structure. The number of array elements is specified by the <b>Count</b> member. The buffer that PoFx allocates to hold this structure is guaranteed to be large enough to contain the <b>PEP_PPM_QUERY_IDLE_STATES</b> structure plus any array elements that follow this structure. Each idle state is identified by its array index. If the array contains N elements, idle state indexes range from 0 to N–1.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629121">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a> notification. The <b>Count</b> member of the structure contains an input value that PoFx supplies when this notification is sent. The other two members contain output values that the PEP writes to the structure in response to the notification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pepfx.h) |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt629121">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186820">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a>



<a href="..\pep_x\ns-pep_x-_pep_processor_idle_state.md">PEP_PROCESSOR_IDLE_STATE</a>