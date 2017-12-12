---
UID: NS.PEPFX._PEP_PLATFORM_IDLE_STATE
title: _PEP_PLATFORM_IDLE_STATE
author: windows-driver-content
description: The PEP_PLATFORM_IDLE_STATE structure specifies the properties of a platform idle state.
old-location: kernel\pep_platform_idle_state.htm
old-project: kernel
ms.assetid: D0503B73-EDFA-4742-BAFA-4FEE56F0A3C8
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _PEP_PLATFORM_IDLE_STATE, *PPEP_PLATFORM_IDLE_STATE, PEP_PLATFORM_IDLE_STATE
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
req.alt-api: PEP_PLATFORM_IDLE_STATE
req.alt-loc: pepfx.h
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
---

# _PEP_PLATFORM_IDLE_STATE structure



## -description
The <b>PEP_PLATFORM_IDLE_STATE</b> structure specifies the properties of a platform idle state.



## -syntax

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


## -struct-fields

### -field InitiatingProcessor

A <b>POHANDLE</b> value that identifies the processor that initiates the transition to this platform idle state, or <b>NULL</b> if any processor can initiate the transition. If non-NULL, this handle represents the registration of the processor (as a device) with the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx).


### -field InitiatingState

The index of the processor idle state that the processor enters to initiate the platform's entry to the specified platform idle state. If the <b>IdleStates</b> array in the <a href="kernel.pep_ppm_query_idle_states_v2">PEP_PPM_QUERY_IDLE_STATES_V2</a> structure contains N elements, the idle states are numbered 0 to Nâ€“1 in the order in which they appear in the array.


### -field Latency

The worst-case latency, in 100-nanosecond units, that the platform requires to wake from this idle state in response to a wake event.


### -field BreakEvenDuration

The minimum amount of time, specified in 100-nanosecond units, that the platform must spend in this idle state to make a transition to this state worthwhile. PoFx uses this member value as a hint to avoid switching the platform to an idle state unless the platform is likely to remain in this state for at least the amount of time specified by <b>BreakEvenDuration</b>.




### -field DependencyArrayUsed

The number of items in <b>DependencyArray</b> which were filled in by the PEP.


### -field DependencyArrayCount

The number of elements in the <b>DependencyArray</b> array. The array contains one element for each processor in the hardware platform.


### -field DependencyArray

The first element in an array of <a href="kernel.pep_processor_idle_dependency">PEP_PROCESSOR_IDLE_DEPENDENCY</a> structures. This array specifies the set of dependencies that the platform idle state has on each processor. If the platform contains N processors, the array contains N elements, and processors are numbered 0 to N-1 in the order in which they are represented in the array.


## -remarks
This structure is used in conjunction with the <a href="kernel.pep_notify_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notification. The <b>State</b> member of a <a href="kernel.pep_ppm_query_platform_state">PEP_PPM_QUERY_PLATFORM_STATE</a> structure is a <b>PEP_PLATFORM_IDLE_STATE</b> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with Windows 10.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Pepfx.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_notify_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a>
</dt>
<dt>
<a href="kernel.pep_ppm_query_idle_states_v2">PEP_PPM_QUERY_IDLE_STATES_V2</a>
</dt>
<dt>
<a href="kernel.pep_ppm_query_platform_state">PEP_PPM_QUERY_PLATFORM_STATE</a>
</dt>
<dt>
<a href="kernel.pep_processor_idle_dependency">PEP_PROCESSOR_IDLE_DEPENDENCY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PLATFORM_IDLE_STATE structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

