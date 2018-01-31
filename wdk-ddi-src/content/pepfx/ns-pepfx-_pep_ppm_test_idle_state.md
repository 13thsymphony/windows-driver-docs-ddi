---
UID : NS:pepfx._PEP_PPM_TEST_IDLE_STATE
title : "_PEP_PPM_TEST_IDLE_STATE"
author : windows-driver-content
description : The PEP_PPM_TEST_IDLE_STATE structure contains information about whether the processor can immediately enter a processor idle state.
old-location : kernel\pep_ppm_test_idle_state.htm
old-project : kernel
ms.assetid : 2B465848-6564-404F-8F5B-E761866278C5
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PPEP_PPM_TEST_IDLE_STATE, pepfx/PEP_PPM_TEST_IDLE_STATE, kernel.pep_ppm_test_idle_state, PEP_PPM_TEST_IDLE_STATE structure [Kernel-Mode Driver Architecture], _PEP_PPM_TEST_IDLE_STATE, pepfx/PPEP_PPM_TEST_IDLE_STATE, PPEP_PPM_TEST_IDLE_STATE structure pointer [Kernel-Mode Driver Architecture], PEP_PPM_TEST_IDLE_STATE, *PPEP_PPM_TEST_IDLE_STATE
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PPEP_PPM_TEST_IDLE_STATE, PEP_PPM_TEST_IDLE_STATE"
---

# _PEP_PPM_TEST_IDLE_STATE structure
The <b>PEP_PPM_TEST_IDLE_STATE</b> structure contains information about whether the processor can immediately enter a processor idle state.

## Syntax
````
typedef struct _PEP_PPM_TEST_IDLE_STATE {
  ULONG ProcessorState;
  ULONG PlatformState;
  ULONG VetoReason;
} PEP_PPM_TEST_IDLE_STATE, *PPEP_PPM_TEST_IDLE_STATE;
````

## Members


`PlatformState`

[in] The index of the platform idle state that the hardware platform will enter when the processor enters the processor idle state specified by <b>ProcessorState</b>. The PEP previously specified the supported platform idle states in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification. If the PEP specified M platform idle states, valid platform-idle-state indexes range from 0 to M-1. If no change in platform idle state will occur, this member will contain the value <b>PEP_PLATFORM_IDLE_STATE_NONE</b> (0xffffffff).

`ProcessorState`

(input) The index of the processor idle state that is to be entered. The platform extension plug-in (PEP) previously specified the supported processor idle states in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. If the PEP specified N processor idle states, valid processor-idle-state indexes range from 0 to N-1.

`VetoReason`

[out] The nonzero index value that identifies reason the PEP needs to veto this idle state transition, or <b>PEP_IDLE_VETO_NONE</b> (0) if the PEP is prepared to immediately make this transition. If the PEP supports N veto reasons, valid veto reason indexes range from 1 to N. The PEP previously specified the number of supported veto reasons in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a> notification.

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186831">PEP_NOTIFY_PPM_TEST_IDLE_STATE</a> notification. The <b>ProcessorState</b> and <b>PlatformState</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The PEP writes an output value to the <b>VetoReason</b> member of this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186831">PEP_NOTIFY_PPM_TEST_IDLE_STATE</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_TEST_IDLE_STATE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>