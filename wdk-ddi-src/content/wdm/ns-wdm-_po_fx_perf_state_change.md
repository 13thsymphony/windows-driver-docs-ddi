---
UID: NS:wdm._PO_FX_PERF_STATE_CHANGE
title: _PO_FX_PERF_STATE_CHANGE
author: windows-driver-content
description: The PO_FX_PERF_STATE_CHANGE structure contains information about a change to a performance state that is being requested by calling the PoFxIssueComponentPerfStateChange or PoFxIssueComponentPerfStateChangeMultiple routine.
old-location: kernel\po_fx_perf_state_change.htm
old-project: kernel
ms.assetid: AE7A79DE-0202-4816-A36C-5A15C4539392
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PO_FX_PERF_STATE_CHANGE, PO_FX_PERF_STATE_CHANGE, *PPO_FX_PERF_STATE_CHANGE
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
req.alt-api: PO_FX_PERF_STATE_CHANGE
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
req.typenames: PO_FX_PERF_STATE_CHANGE, *PPO_FX_PERF_STATE_CHANGE
req.product: Windows 10 or later.
---

# _PO_FX_PERF_STATE_CHANGE structure



## -description
The <b>PO_FX_PERF_STATE_CHANGE</b> structure contains information about a change to a performance state that is being requested by calling the <a href="..\wdm\nf-wdm-pofxissuecomponentperfstatechange.md">PoFxIssueComponentPerfStateChange</a> or <a href="..\wdm\nf-wdm-pofxissuecomponentperfstatechangemultiple.md">PoFxIssueComponentPerfStateChangeMultiple</a> routine.



## -syntax

````
typedef struct _PO_FX_PERF_STATE_CHANGE {
  ULONG Set;
  union {
    ULONG     StateIndex;
    ULONGLONG StateValue;
  };
} PO_FX_PERF_STATE_CHANGE, *PPO_FX_PERF_STATE_CHANGE;
````


## -struct-fields

### -field Set

The index of the performance state set that is being changed within the collection of performance state sets for the component.


### -field StateIndex

For sets that represent a discrete number of performance states (that is, where the <b>Type</b> member of the <a href="..\wdm\ns-wdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a> is <b>PoFxPerfStateTypeDiscrete</b>), this member is the index of the performance state to use for the new performance level.


### -field StateValue

For sets that represent a continuous distribution of performance states (that is, where the <b>Type</b> member of the <a href="..\wdm\ns-wdm-_po_fx_component_perf_set.md">PO_FX_COMPONENT_PERF_SET</a> is <b>PoFxPerfStateTypeRange</b>), this member is the value of the performance state to use for the new performance level.


## -remarks
The <b>PO_FX_PERF_STATE_CHANGE</b> structure is used for the <i>PerfChange</i> parameter of the <a href="..\wdm\nf-wdm-pofxissuecomponentperfstatechange.md">PoFxIssueComponentPerfStateChange</a> routine and the  <i>PerfChanges</i> parameter of the <a href="..\wdm\nf-wdm-pofxissuecomponentperfstatechangemultiple.md">PoFxIssueComponentPerfStateChangeMultiple</a> routine. 


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
<a href="https://msdn.microsoft.com/D5341D6D-7C71-43CB-9C70-7E939B32C33F">Device Performance State Management</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-pofxissuecomponentperfstatechange.md">PoFxIssueComponentPerfStateChange</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-pofxissuecomponentperfstatechangemultiple.md">PoFxIssueComponentPerfStateChangeMultiple</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PO_FX_PERF_STATE_CHANGE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

