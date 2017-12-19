---
UID: NC.pepfx.POFXCALLBACKUPDATEPROCESSORIDLESTATE
title: POFXCALLBACKUPDATEPROCESSORIDLESTATE
author: windows-driver-content
description: The UpdateProcessorIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified processor idle state.
old-location: kernel\updateprocessoridlestate.htm
old-project: kernel
ms.assetid: 023A2637-A79A-4ADE-B54C-646CBDDF08B8
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _VPCI_PNP_ID, PVPCI_PNP_ID, *PVPCI_PNP_ID, VPCI_PNP_ID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UpdateProcessorIdleState
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

# POFXCALLBACKUPDATEPROCESSORIDLESTATE callback



## -description
The <b>UpdateProcessorIdleState</b> routine is called by the platform extension plug-in (PEP) to update the properties of the specified processor idle state.



## -prototype

````
POFXCALLBACKUPDATEPROCESSORIDLESTATE UpdateProcessorIdleState;

NTSTATUS UpdateProcessorIdleState(
  _In_ POHANDLE                         ProcessorHandle,
  _In_ ULONG                            ProcessorState,
  _In_ PPEP_PROCESSOR_IDLE_STATE_UPDATE Update
)
{ ... }
````


## -parameters

### -param ProcessorHandle [in]

A POHANDLE value that represents the registration of the processor (as a device) with the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx). The PEP previously received this handle from PoFx during the <a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the processor had been registered with PoFx.


### -param ProcessorState [in]

An index that identifies the processor idle state whose properties are to be updated. In response to a previous <a href="kernel.pep_notify_ppm_query_idle_states_v2">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification, the PEP specified the number of supported processor idle states and the properties of these states. If the PEP specified N processor idle states, valid processor idle state indexes range from 0 to N-â€“1.


### -param Update [in]

A pointer to a <a href="kernel.pep_processor_idle_state_update">PEP_PROCESSOR_IDLE_STATE_UPDATE</a> structure that contains the updated properties of the processor idle state.


## -returns
<b>UpdateProcessorIdleState</b> returns STATUS_SUCCESS if it successfully updates the properties of the processor idle state. Possible error return values include the following status codes.
<dl>
<dt>STATUS_NOT_SUPPORTED</dt>
</dl>The version number in the <b>PEP_PROCESSOR_IDLE_STATE_UPDATE</b> structure is not a supported value.
<dl>
<dt>STATUS_NOT_IMPLEMENTED</dt>
</dl>The <b>UpdateProcessorIdleState</b> routine is not implemented for this processor.

 


## -remarks
This routine is implemented by PoFx and is called by the PEP. The <b>UpdateProcessorIdleState</b> member of the <a href="kernel.pep_kernel_information_struct_v3">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>UpdateProcessorIdleState</b> routine.

The <b>UpdateProcessorIdleState</b> routine must be called at IRQL = PASSIVE_LEVEL.


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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a>
</dt>
<dt>
<a href="kernel.pep_kernel_information_struct_v3">PEP_KERNEL_INFORMATION_STRUCT_V3</a>
</dt>
<dt>
<a href="kernel.pep_processor_idle_state_update">PEP_PROCESSOR_IDLE_STATE_UPDATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKUPDATEPROCESSORIDLESTATE routine%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

