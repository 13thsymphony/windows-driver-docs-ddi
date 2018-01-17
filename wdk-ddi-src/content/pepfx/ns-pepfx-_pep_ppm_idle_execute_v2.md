---
UID: NS:pepfx._PEP_PPM_IDLE_EXECUTE_V2
title: _PEP_PPM_IDLE_EXECUTE_V2
author: windows-driver-content
description: The PEP_PPM_IDLE_EXECUTE_V2 structure specifies the idle state that the processor is to enter.
old-location: kernel\pep_ppm_idle_execute_v2.htm
old-project: kernel
ms.assetid: 28CF8291-E7C3-4289-909C-C89D350A9D83
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PEP_PPM_IDLE_EXECUTE_V2, *PPEP_PPM_IDLE_EXECUTE_V2, PEP_PPM_IDLE_EXECUTE_V2
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
req.alt-api: PEP_PPM_IDLE_EXECUTE_V2
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
req.typenames: *PPEP_PPM_IDLE_EXECUTE_V2, PEP_PPM_IDLE_EXECUTE_V2
---

# _PEP_PPM_IDLE_EXECUTE_V2 structure



## -description
The <b>PEP_PPM_IDLE_EXECUTE_V2</b> structure specifies the idle state that the processor is to enter.



## -syntax

````
typedef struct _PEP_PPM_IDLE_EXECUTE_V2 {
  NTSTATUS                                   Status;
  ULONG                                      ProcessorState;
  ULONG                                      PlatformState;
  ULONG                                      CoordinatedStateCount;
  _Field_size_(CoordinatedStateCount) PULONG CoordinatedStates;
} PEP_PPM_IDLE_EXECUTE_V2, *PPEP_PPM_IDLE_EXECUTE_V2;
````


## -struct-fields

### -field Status

[out] An <b>NTSTATUS</b> value that indicates whether the processor idle state transition was successful. The platform extension plug-in (PEP) sets this member to <b>STATUS_SUCCESSFUL</b> if the transition succeeded. Otherwise, this member is set to an appropriate error status code.


### -field ProcessorState

[in] The index of the processor idle state that the processor is to enter. The PEP previously specified the supported processor idle states in response to a <a href="kernel.pep_notify_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. If the PEP specified N processor idle states, valid processor-idle-state indexes range from 0 to N-1.


### -field PlatformState

[in] The index of the platform idle state that the hardware platform will enter when the processor enters the processor idle state specified by <b>ProcessorState</b>. The PEP previously specified the supported platform idle states in response to a <a href="kernel.pep_notify_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification. If the PEP specified M platform idle states, valid platform-idle-state indexes range from 0 to M-1. If no change in platform idle state will occur, this member will contain the value <b>PEP_PLATFORM_IDLE_STATE_NONE</b> (0xffffffff).


### -field CoordinatedStateCount

Supplies the number of coordinated idle states being entered by this transition.


### -field CoordinatedStates

Supplies a pointer to an array of coordinated idle states that are being entered by this transition.


## -remarks
This structure is used by the <a href="kernel.pep_notify_ppm_idle_execute">PEP_NOTIFY_PPM_IDLE_EXECUTE</a> notification. The <b>ProcessorState</b> and <b>PlatformState</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The <b>Status</b> member contains an output value that the PEP writes to this member.


## -see-also
<dl>
<dt>
<a href="kernel.pep_notify_ppm_idle_execute">PEP_NOTIFY_PPM_IDLE_EXECUTE</a>
</dt>
<dt>
<a href="kernel.pep_notify_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>
</dt>
<dt>
<a href="kernel.pep_notify_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_IDLE_EXECUTE_V2 structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

