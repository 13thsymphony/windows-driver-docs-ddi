---
UID: NS.PEP_X._PEP_PPM_QUERY_IDLE_STATES
title: _PEP_PPM_QUERY_IDLE_STATES
author: windows-driver-content
description: The PEP_PPM_QUERY_IDLE_STATES structure describes the idle states of a particular processor.
old-location: kernel\pep_ppm_query_idle_states.htm
old-project: kernel
ms.assetid: 27B43684-6564-41A0-9F0D-D49F88D1F14D
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _PEP_PPM_QUERY_IDLE_STATES, PEP_PPM_QUERY_IDLE_STATES, *PPEP_PPM_QUERY_IDLE_STATES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: Pepfx.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_PPM_QUERY_IDLE_STATES
req.alt-loc: pep_x.h
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

# _PEP_PPM_QUERY_IDLE_STATES structure



## -description
The <b>PEP_PPM_QUERY_IDLE_STATES</b> structure describes the idle states of a particular processor.



## -syntax

````
typedef struct _PEP_PPM_QUERY_IDLE_STATES {
  ULONG                    Count;
  ULONG                    MaximumCoordinatedProcessors;
  PEP_PROCESSOR_IDLE_STATE IdleStates[ANYSIZE_ARRAY];
} PEP_PPM_QUERY_IDLE_STATES, *PPEP_PPM_QUERY_IDLE_STATES;
````


## -struct-fields

### -field Count

[in] The number of elements in the <b>IdleStates</b> array. This member is set to the <b>IdleStateCount</b> value that the PEP previously supplied for this processor in response to the <a href="kernel.pep_notify_ppm_query_capabilities">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a> notification.


### -field MaximumCoordinatedProcessors

[out] The maximum number of secondary processors that are subordinate to this processor for any transitions to idle states. A primary processor can enter the selected idle state only after the secondary processors have entered their corresponding idle states. The PEP must set the <b>MaximumCoordinatedProcessors</b> member to a number that is less than the total number of processors in the hardware platform.


### -field IdleStates

[in] The first element in an array of <a href="kernel.pep_processor_idle_state">PEP_PROCESSOR_IDLE_STATE</a> structures. Each array element describes one of the idle states of this processor. If the array contains more than one element, the additional elements immediately follow the end of the <b>PEP_PPM_QUERY_IDLE_STATES</b> structure. The number of array elements is specified by the <b>Count</b> member. The buffer that PoFx allocates to hold this structure is guaranteed to be large enough to contain the <b>PEP_PPM_QUERY_IDLE_STATES</b> structure plus any array elements that follow this structure. Each idle state is identified by its array index. If the array contains N elements, idle state indexes range from 0 to N–1.


## -remarks
This structure is used by the <a href="kernel.pep_notify_ppm_query_idle_states">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a> notification. The <b>Count</b> member of the structure contains an input value that PoFx supplies when this notification is sent. The other two members contain output values that the PEP writes to the structure in response to the notification.


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
<dt>Pep_x.h (include Pepfx.h)</dt>
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
<a href="kernel.pep_notify_ppm_query_idle_states">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a>
</dt>
<dt>
<a href="kernel.pep_processor_idle_state">PEP_PROCESSOR_IDLE_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_IDLE_STATES structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

