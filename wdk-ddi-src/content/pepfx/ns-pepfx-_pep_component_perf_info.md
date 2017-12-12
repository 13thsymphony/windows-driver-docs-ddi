---
UID: NS.PEPFX._PEP_COMPONENT_PERF_INFO
title: _PEP_COMPONENT_PERF_INFO
author: windows-driver-content
description: The PEP_COMPONENT_PERF_INFO structure describes the performance states (P-states) of a component.
old-location: kernel\pep_component_perf_info.htm
old-project: kernel
ms.assetid: F05D67A0-6583-4C3E-B9AA-B99381A18047
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _PEP_COMPONENT_PERF_INFO, *PPEP_COMPONENT_PERF_INFO, PEP_COMPONENT_PERF_INFO
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
req.alt-api: PEP_COMPONENT_PERF_INFO
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

# _PEP_COMPONENT_PERF_INFO structure



## -description
The <b>PEP_COMPONENT_PERF_INFO</b> structure describes the performance states (P-states) of a component.



## -syntax

````
typedef struct _PEP_COMPONENT_PERF_INFO {
  ULONG                  SetCount;
  PEP_COMPONENT_PERF_SET PerfStateSets[ANYSIZE_ARRAY];
} PEP_COMPONENT_PERF_INFO, *PPEP_COMPONENT_PERF_INFO;
````


## -struct-fields

### -field SetCount

The number of elements in the <b>PerfStateSets</b> array.


### -field PerfStateSets

The first element in an array of <a href="kernel.pep_component_perf_set">PEP_COMPONENT_PERF_SET</a> structures. Each array element describes a P-state of the component. If the array contains more than one element, the additional elements immediately follow the end of the <b>PEP_COMPONENT_PERF_INFO</b> structure.


## -remarks
This structure is used in conjunction with the <a href="kernel.pep_dpm_register_component_perf_states">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a> notification. The <b>PerfStateSets</b> member of the <a href="kernel.pep_register_component_perf_states">PEP_REGISTER_COMPONENT_PERF_STATES</a> structure is a <b>PEP_COMPONENT_PERF_INFO</b> structure.

The <b>PEP_COMPONENT_PERF_INFO</b> structure contains input values that are supplied by the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx). The platform extension plug-in (PEP) must not write to this structure.


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
<a href="kernel.pep_component_perf_info">PEP_COMPONENT_PERF_INFO</a>
</dt>
<dt>
<a href="kernel.pep_component_perf_set">PEP_COMPONENT_PERF_SET</a>
</dt>
<dt>
<a href="kernel.pep_dpm_register_component_perf_states">PEP_DPM_REGISTER_COMPONENT_PERF_STATES</a>
</dt>
<dt>
<a href="kernel.pep_register_component_perf_states">PEP_REGISTER_COMPONENT_PERF_STATES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_COMPONENT_PERF_INFO structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

