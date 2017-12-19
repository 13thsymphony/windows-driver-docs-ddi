---
UID: NS.WDM._PO_FX_COMPONENT_PERF_INFO
title: _PO_FX_COMPONENT_PERF_INFO
author: windows-driver-content
description: The PO_FX_COMPONENT_PERF_INFO structure describes all the sets of performance states for a single component within a device.
old-location: kernel\po_fx_component_perf_info.htm
old-project: kernel
ms.assetid: DA9C020F-18E7-4C6C-AEBB-81B099C80CD0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _PO_FX_COMPONENT_PERF_INFO, *PPO_FX_COMPONENT_PERF_INFO, PPO_FX_COMPONENT_PERF_INFO, PO_FX_COMPONENT_PERF_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PO_FX_COMPONENT_PERF_INFO
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _PO_FX_COMPONENT_PERF_INFO structure



## -description
The <b>PO_FX_COMPONENT_PERF_INFO</b> structure describes  all the sets of performance states for a  single component within a device.



## -syntax

````
typedef struct _PO_FX_COMPONENT_PERF_INFO {
  ULONG                    PerfStateSetsCount;
  PO_FX_COMPONENT_PERF_SET PerfStateSets[ANYSIZE_ARRAY];
} PO_FX_COMPONENT_PERF_INFO, *PPO_FX_COMPONENT_PERF_INFO;
````


## -struct-fields

### -field PerfStateSetsCount

The number of elements in the array <b>PerfStateSets</b> array.


### -field PerfStateSets

This member is the first element in an array of one or more <a href="kernel.po_fx_component_perf_set">PO_FX_COMPONENT_PERF_SET</a> elements. Each  <b>PO_FX_COMPONENT_PERF_SET</b> represents one set of supported performance states for a component. If the array contains more than one element, the additional elements immediately follow the first element.


## -remarks
When a device driver calls the <a href="kernel.pofxregistercomponentperfstates">PoFxRegisterComponentPerfStates</a> routine to register a component for performance state support with the power management framework (PoFx),  the driver can supply a <b>PO_FX_COMPONENT_PERF_INFO</b> structure that  describes the sets of the performance states supported by the component. The <b>PerfStateSets</b> member of the <b>PO_FX_COMPONENT_PERF_INFO</b> structure contains an array of <a href="kernel.po_fx_component_perf_set">PO_FX_COMPONENT_PERF_SET</a> structures that represent the supported performance states.

Most drivers are expected to define a single set of performance states per component. For example, a driver might define one set of performance states to control the clock frequency for a component. However, some drivers may need to define more than one performance state set to control multiple dimensions of performance states for a component. For example, a driver might define two sets of performance states to control the clock frequency and bus bandwidth.


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
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn939352">Component-Level Performance State Management</a>
</dt>
<dt>
<a href="kernel.pofxregistercomponentperfstates">PoFxRegisterComponentPerfStates</a>
</dt>
<dt>
<a href="kernel.po_fx_component_perf_set">PO_FX_COMPONENT_PERF_SET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_COMPONENT_PERF_INFO structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

