---
UID: NS:pep_x._PEP_PPM_PARK_SELECTION_V2
title: "_PEP_PPM_PARK_SELECTION_V2"
author: windows-driver-content
description: The PEP_PPM_PARK_SELECTION_V2 structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption.
old-location: kernel\pep_ppm_park_selection_v2.htm
old-project: kernel
ms.assetid: D1EFB30D-E8E2-4585-AB0E-B7903F4D6656
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_PPM_PARK_SELECTION_V2, PEP_PPM_PARK_SELECTION_V2, PEP_PPM_PARK_SELECTION_V2 structure [Kernel-Mode Driver Architecture], PPEP_PPM_PARK_SELECTION_V2, PPEP_PPM_PARK_SELECTION_V2 structure pointer [Kernel-Mode Driver Architecture], PROCESSOR_PARK_TYPE_CORE_PARKING, PROCESSOR_PARK_TYPE_INTERRUPT_STEERING, _PEP_PPM_PARK_SELECTION_V2, kernel.pep_ppm_park_selection_v2, pepfx/PEP_PPM_PARK_SELECTION_V2, pepfx/PPEP_PPM_PARK_SELECTION_V2"
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
-	PEP_PPM_PARK_SELECTION_V2
product: Windows
targetos: Windows
req.typenames: PEP_PPM_PARK_SELECTION_V2, *PPEP_PPM_PARK_SELECTION_V2, PEP_PPM_PARK_SELECTION_V2, *PPEP_PPM_PARK_SELECTION_V2
---

# _PEP_PPM_PARK_SELECTION_V2 structure
The <b>PEP_PPM_PARK_SELECTION_V2</b> structure indicates the preferences of the operating system and platform extension plug-in (PEP) regarding which processors in the platform should be parked to reduce power consumption.

## Syntax
```
typedef struct _PEP_PPM_PARK_SELECTION_V2 {
  ULONG                          AdditionalUnparkedProcessors;
  ULONG                          Count;
  PPEP_PROCESSOR_PARK_PREFERENCE Processors;
  ULONGLONG                      EvaluationTime;
  UCHAR                          EvaluationType;
} PEP_PPM_PARK_SELECTION_V2, *PPEP_PPM_PARK_SELECTION_V2;
```

## Members


`AdditionalUnparkedProcessors`

[in] The number of additional processors that need to be unparked.

This number includes all processors in the <b>Processors</b> array for which the PEP sets <b>PepPreference</b> to PROCESSOR_PARK_PREFERENCE_PARKED but the operating system sets <b>PoPreference</b> to either PROCESSOR_PARK_PREFERENCE_UNPARKED or PROCESSOR_PARK_PREFERENCE_NONE. For more information about these values, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt186837">PEP_PROCESSOR_PARK_PREFERENCE</a>.

This number does not include processors in the <b>Processors</b> array for which the operating system sets the <b>PoPreference</b> value to PROCESSOR_PARK_PREFERENCE_PARKED.

`Count`

[in] The number of elements in the array pointed to by the <b>Processors</b> member.

`Processors`

[in/out] A pointer to an array of <a href="https://msdn.microsoft.com/library/windows/hardware/mt186837">PEP_PROCESSOR_PARK_PREFERENCE</a> structures. Each array element indicates the parking preferences for a particular processor. The <b>Count</b> member specifies the number of elements in the array.

`EvaluationTime`

The interrupt time of the performance check evaluation that initiated this notification.

`EvaluationType`

The type of evaluation being performed. This can be one of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="PROCESSOR_PARK_TYPE_CORE_PARKING"></a><a id="processor_park_type_core_parking"></a><dl>
<dt><b>PROCESSOR_PARK_TYPE_CORE_PARKING</b></dt>
<dt>0x00</dt>
</dl>
</td>
<td width="60%">
The processor should be parked.

</td>
</tr>
<tr>
<td width="40%"><a id="PROCESSOR_PARK_TYPE_INTERRUPT_STEERING"></a><a id="processor_park_type_interrupt_steering"></a><dl>
<dt><b>PROCESSOR_PARK_TYPE_INTERRUPT_STEERING</b></dt>
<dt>0x01</dt>
</dl>
</td>
<td width="60%">
Interrupts should be steered away from the processor.

</td>
</tr>
</table>

## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186770">PEP_NOTIFY_PPM_PARK_SELECTION_V2 notification</a> notification. All three members of the structure contain input values that are set by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) before this notification is sent to the PEP.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h (include Pep_x.h) |