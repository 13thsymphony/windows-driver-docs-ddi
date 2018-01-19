---
UID : NS:pepfx._PEP_PLATFORM_IDLE_STATE
title : _PEP_PLATFORM_IDLE_STATE
author : windows-driver-content
description : The PEP_PLATFORM_IDLE_STATE structure specifies the properties of a platform idle state.
old-location : kernel\pep_platform_idle_state.htm
old-project : kernel
ms.assetid : D0503B73-EDFA-4742-BAFA-4FEE56F0A3C8
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _PEP_PLATFORM_IDLE_STATE, PEP_PLATFORM_IDLE_STATE, *PPEP_PLATFORM_IDLE_STATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : pepfx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Supported starting with Windows 10.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PEP_PLATFORM_IDLE_STATE
req.alt-loc : pepfx.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : PEP_PLATFORM_IDLE_STATE, *PPEP_PLATFORM_IDLE_STATE
---

# _PEP_PLATFORM_IDLE_STATE structure
The <b>PEP_PLATFORM_IDLE_STATE</b> structure specifies the properties of a platform idle state.

## Syntax
````
typedef struct _PEP_PLATFORM_IDLE_STATE {
  POHANDLE                                                                                   InitiatingProcessor;
  UCHAR                                                                                      InitiatingState;
  ULONG                                                                                      Latency;
  ULONG                                                                                      BreakEvenDuration;
  _Field_range_(0, DependencyArrayCount) ULONG                                               DependencyArrayUsed;
  ULONG                                                                                      DependencyArrayCount;
  _Field_size_part_(DependencyArrayCount, DependencyArrayUsed) PEP_PROCESSOR_IDLE_DEPENDENCY DependencyArray[ANYSIZE_ARRAY];
} PEP_PLATFORM_IDLE_STATE, *PPEP_PLATFORM_IDLE_STATE;
````

## Members

        
            `BreakEvenDuration`

            The minimum amount of time, specified in 100-nanosecond units, that the platform must spend in this idle state to make a transition to this state worthwhile. PoFx uses this member value as a hint to avoid switching the platform to an idle state unless the platform is likely to remain in this state for at least the amount of time specified by <b>BreakEvenDuration</b>.
        
            `DependencyArray`

            The first element in an array of <a href="..\pepfx\ns-pepfx-_pep_processor_idle_dependency.md">PEP_PROCESSOR_IDLE_DEPENDENCY</a> structures. This array specifies the set of dependencies that the platform idle state has on each processor. If the platform contains N processors, the array contains N elements, and processors are numbered 0 to N-1 in the order in which they are represented in the array.
        
            `DependencyArrayCount`

            The number of elements in the <b>DependencyArray</b> array. The array contains one element for each processor in the hardware platform.
        
            `DependencyArrayUsed`

            The number of items in <b>DependencyArray</b> which were filled in by the PEP.
        
            `InitiatingProcessor`

            A <b>POHANDLE</b> value that identifies the processor that initiates the transition to this platform idle state, or <b>NULL</b> if any processor can initiate the transition. If non-NULL, this handle represents the registration of the processor (as a device) with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).
        
            `InitiatingState`

            The index of the processor idle state that the processor enters to initiate the platform's entry to the specified platform idle state. If the <b>IdleStates</b> array in the <a href="..\pepfx\ns-pepfx-_pep_ppm_query_idle_states_v2.md">PEP_PPM_QUERY_IDLE_STATES_V2</a> structure contains N elements, the idle states are numbered 0 to Nâ€“1 in the order in which they appear in the array.
        
            `Latency`

            The worst-case latency, in 100-nanosecond units, that the platform requires to wake from this idle state in response to a wake event.

    ## Remarks
        This structure is used in conjunction with the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notification. The <b>State</b> member of a <a href="..\pepfx\ns-pepfx-_pep_ppm_query_platform_state.md">PEP_PPM_QUERY_PLATFORM_STATE</a> structure is a <b>PEP_PLATFORM_IDLE_STATE</b> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |

    ## See Also

        <dl>
<dt>
<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_ppm_query_idle_states_v2.md">PEP_PPM_QUERY_IDLE_STATES_V2</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_ppm_query_platform_state.md">PEP_PPM_QUERY_PLATFORM_STATE</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx-_pep_processor_idle_dependency.md">PEP_PROCESSOR_IDLE_DEPENDENCY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PLATFORM_IDLE_STATE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>