---
UID: NS.PEPFX._PEP_PPM_QUERY_IDLE_STATES_V2
title: _PEP_PPM_QUERY_IDLE_STATES_V2
author: windows-driver-content
description: The PEP_PPM_QUERY_IDLE_STATES_V2 structure is used during processor initialization to query the platform extension plug-in (PEP) for a list of processor idle states that the processor supports.
old-location: kernel\pep_ppm_query_idle_states_v2.htm
old-project: kernel
ms.assetid: 0C225F3B-0D09-48FD-9BD3-F17D5E602698
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _PEP_PPM_QUERY_IDLE_STATES_V2, *PPEP_PPM_QUERY_IDLE_STATES_V2, PEP_PPM_QUERY_IDLE_STATES_V2
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
req.alt-api: PEP_PPM_QUERY_IDLE_STATES_V2
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

# _PEP_PPM_QUERY_IDLE_STATES_V2 structure



## -description
The <b>PEP_PPM_QUERY_IDLE_STATES_V2</b> structure is used during processor initialization to query the platform extension plug-in (PEP) for a list of processor idle states that the processor supports.


## -syntax

````
typedef struct _PEP_PPM_QUERY_IDLE_STATES_V2 {
  ULONG                       Count;
  PEP_PROCESSOR_IDLE_STATE_V2 IdleStates[ANYSIZE_ARRAY];
} PEP_PPM_QUERY_IDLE_STATES_V2, *PPEP_PPM_QUERY_IDLE_STATES_V2;
````


## -struct-fields

### -field Count

[in] The number of elements in the <b>IdleStates</b> array. The Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx) previously sent the PEP a <a href="kernel.pep_notify_ppm_query_capabilities">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a> notification to determine this number.

### -field IdleStates

[out] The first element in an array of <a href="kernel.pep_processor_idle_state_v2">PEP_PROCESSOR_IDLE_STATE_V2</a> structures that describe the processor idle states. If this array contains more than one element, the addition array elements follow the end of the <b>PEP_PPM_QUERY_IDLE_STATES_V2</b> structure.

## -remarks
This structure is used by the <a href="kernel.pep_notify_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. The <b>Count</b> member of the <b>PEP_PPM_QUERY_IDLE_STATES_V2</b> structure contains an input value that is supplied by the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx). The <b>IdleStates</b> array elements contain output values that the PEP writes to the structure in response to this notification.

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
<a href="kernel.pep_notify_ppm_query_capabilities">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a>
</dt>
<dt>
<a href="kernel.pep_notify_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>
</dt>
<dt>
<a href="kernel.pep_processor_idle_state_v2">PEP_PROCESSOR_IDLE_STATE_V2</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_IDLE_STATES_V2 structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
