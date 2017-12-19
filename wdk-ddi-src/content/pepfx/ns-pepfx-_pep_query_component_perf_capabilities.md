---
UID: NS.PEPFX._PEP_QUERY_COMPONENT_PERF_CAPABILITIES
title: _PEP_QUERY_COMPONENT_PERF_CAPABILITIES
author: windows-driver-content
description: The PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure specifies the number of performance state (P-state) sets that are defined for a component.
old-location: kernel\pep_query_component_perf_capabilities.htm
old-project: kernel
ms.assetid: 6E1A4A3B-FA8B-4AAC-898F-CCFF77BFA962
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _PEP_QUERY_COMPONENT_PERF_CAPABILITIES, PEP_QUERY_COMPONENT_PERF_CAPABILITIES, *PPEP_QUERY_COMPONENT_PERF_CAPABILITIES
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
req.alt-api: PEP_QUERY_COMPONENT_PERF_CAPABILITIES
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

# _PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure



## -description
The <b>PEP_QUERY_COMPONENT_PERF_CAPABILITIES</b> structure specifies the number of performance state (P-state) sets that are defined for a component.



## -syntax

````
typedef struct _PEP_QUERY_COMPONENT_PERF_CAPABILITIES {
  PEPHANDLE DeviceHandle;
  ULONG     Component;
  ULONG     SetCount;
} PEP_QUERY_COMPONENT_PERF_CAPABILITIES, *PPEP_QUERY_COMPONENT_PERF_CAPABILITIES;
````


## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="kernel.pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -field SetCount

[out] The number of P-state sets that are defined for this component.


## -remarks
This structure is used by the <a href="kernel.pep_dpm_query_component_perf_capabilities">PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES</a> notification. The <b>DeviceHandle</b> and <b>Component</b> members contain input values that are supplied by the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx) when this notification is sent. The <b>SetCount</b> member contains an output value that the PEP writes to the structure in response to the notification.


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
<a href="kernel.pep_device_register_v2">PEP_DEVICE_REGISTER_V2</a>
</dt>
<dt>
<a href="kernel.pep_dpm_query_component_perf_capabilities">PEP_DPM_QUERY_COMPONENT_PERF_CAPABILITIES</a>
</dt>
<dt>
<a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_QUERY_COMPONENT_PERF_CAPABILITIES structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

