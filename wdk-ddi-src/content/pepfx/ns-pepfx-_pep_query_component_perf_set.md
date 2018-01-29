---
UID : NS:pepfx._PEP_QUERY_COMPONENT_PERF_SET
title : _PEP_QUERY_COMPONENT_PERF_SET
author : windows-driver-content
description : The PEP_QUERY_COMPONENT_PERF_SET structure contains query information about a set of performance state values (P-state set) for a component.
old-location : kernel\pep_query_component_perf_set.htm
old-project : kernel
ms.assetid : F870E56B-5D80-4E9C-A06E-D21A9BFA1ED8
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : "*PPEP_QUERY_COMPONENT_PERF_SET, PPEP_QUERY_COMPONENT_PERF_SET structure pointer [Kernel-Mode Driver Architecture], PEP_QUERY_COMPONENT_PERF_SET, kernel.pep_query_component_perf_set, PPEP_QUERY_COMPONENT_PERF_SET, pepfx/PEP_QUERY_COMPONENT_PERF_SET, pepfx/PPEP_QUERY_COMPONENT_PERF_SET, _PEP_QUERY_COMPONENT_PERF_SET, PEP_QUERY_COMPONENT_PERF_SET structure [Kernel-Mode Driver Architecture]"
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
req.typenames : "*PPEP_QUERY_COMPONENT_PERF_SET, PEP_QUERY_COMPONENT_PERF_SET"
---

# _PEP_QUERY_COMPONENT_PERF_SET structure
The <b>PEP_QUERY_COMPONENT_PERF_SET</b> structure contains query information about a set of performance state values (P-state set) for a component.

## Syntax
````
typedef struct _PEP_QUERY_COMPONENT_PERF_SET {
  PEPHANDLE           DeviceHandle;
  ULONG               Component;
  ULONG               Set;
  ULONGLONG           Flags;
  PEP_PERF_STATE_UNIT Unit;
  PEP_PERF_STATE_TYPE Type;
  union {
    struct {
      ULONG Count;
    } Discrete;
    struct {
      ULONGLONG Minimum;
      ULONGLONG Maximum;
    } Range;
  };
} PEP_QUERY_COMPONENT_PERF_SET, *PPEP_QUERY_COMPONENT_PERF_SET;
````

## Members


`Component`

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.

`DeviceHandle`

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.

`Flags`

[in] A set of input flags. No flag bits are currently defined for this member, which is always zero.

`Set`

[in] The index that identifies this P-state set. If this component has M P-state sets, P-state set indexes range from 0 to M–1. The PEP previously specified the number of P-state sets in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186839">PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES</a> notification.

`Type`

[out] A <a href="..\pepfx\ne-pepfx-_pep_perf_state_type.md">PEP_PERF_STATE_TYPE</a> enumeration value that indicates whether the performance values for this P-state set are expressed as a list of discrete values or as a continuous range of values.

`Unit`

[out] A <a href="..\pepfx\ne-pepfx-_pep_perf_state_unit.md">PEP_PERF_STATE_UNIT</a> enumeration value that indicates whether the values for this P-state set are expressed in hertz (frequency units) or bits per second (bandwidth units).

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186840">PEP_DPM_QUERY_COMPONENT_PERF_SET</a> notification. The <b>DeviceHandle</b>, <b>Component</b>, <b>Set</b>, and <b>Flags</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent. The <b>Discrete</b> member or <b>Range</b> member contains an output value that the PEP writes to the structure in response to the notification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | pepfx.h |

## See Also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>

<a href="..\pepfx\ne-pepfx-_pep_perf_state_type.md">PEP_PERF_STATE_TYPE</a>

<a href="..\pepfx\ns-pepfx-_pep_device_register_v2.md">PEP_DEVICE_REGISTER_V2</a>

<a href="..\pepfx\ne-pepfx-_pep_perf_state_unit.md">PEP_PERF_STATE_UNIT</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186840">PEP_DPM_QUERY_COMPONENT_PERF_SET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_QUERY_COMPONENT_PERF_SET structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>