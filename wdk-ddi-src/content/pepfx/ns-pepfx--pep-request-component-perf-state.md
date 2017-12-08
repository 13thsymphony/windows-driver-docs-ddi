---
UID: NS.pepfx._PEP_REQUEST_COMPONENT_PERF_STATE
title: PEP_REQUEST_COMPONENT_PERF_STATE
author: windows-driver-content
description: The PEP_REQUEST_COMPONENT_PERF_STATE structure contains a list of performance state (P-state) changes requested by the Windows power management framework (PoFx), plus status information about the handling of these requests by the platform extension plug-in (PEP).
old-location: kernel\pep_request_component_perf_state.htm
old-project: kernel
ms.assetid: 8334434D-D2FC-4967-8234-3C097908C70B
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PEP_REQUEST_COMPONENT_PERF_STATE, PEP_REQUEST_COMPONENT_PERF_STATE, *PPEP_REQUEST_COMPONENT_PERF_STATE
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
req.alt-api: PEP_REQUEST_COMPONENT_PERF_STATE
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
req.iface: 
---

# PEP_REQUEST_COMPONENT_PERF_STATE structure



## -description
<p>The <b>PEP_REQUEST_COMPONENT_PERF_STATE</b> structure contains a list of performance state (P-state) changes requested by the Windows <a href="kernel.power_management_framework__pofx__routines">power management framework</a> (PoFx), plus status information about the handling of these requests by the platform extension plug-in (PEP).</p>


## -syntax

````
typedef struct _PEP_REQUEST_COMPONENT_PERF_STATE {
  PEPHANDLE                         DeviceHandle;
  ULONG                             Component;
  BOOLEAN                           Completed;
  BOOLEAN                           Succeeded;
  ULONG                             PerfRequestsCount;
  PPEP_COMPONENT_PERF_STATE_REQUEST PerfRequests;
} PEP_REQUEST_COMPONENT_PERF_STATE, *PPEP_REQUEST_COMPONENT_PERF_STATE;
````


## -struct-fields
<dl>

### -field DeviceHandle

<dd>
<p>[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a> notification.</p>
</dd>

### -field Component

<dd>
<p>[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="..\pepfx\ns-pepfx--pep-device-register-v2.md">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.</p>
</dd>

### -field Completed

<dd>
<p>[out] Whether the PEP has completed the requested P-state changes. Set to TRUE to indicate that the P-state changes completed synchronously. Set to FALSE to indicate that the requested P-state changes are pending and will be completed asynchronously by a PEP worker thread. For more information, see Remarks.</p>
</dd>

### -field Succeeded

<dd>
<p>[out] Whether the requested P-state changes successfully completed. Set to TRUE if the PEP successfully completed all P-state changes requested in the <b>PerfRequests</b> array. Set to FALSE if the PEP was unable to perform all the requested P-state changes, in which case the P-states in the hardware were left unchanged. The <b>Succeeded</b> member is used only for <i>synchronous</i> P-state changes. If the PEP sets <b>Completed</b> to FALSE, PoFx ignores the value in the <b>Succeeded</b> member.</p>
</dd>

### -field PerfRequestsCount

<dd>
<p>[in] The number of P-state changes requested in the array pointed to by the <b>PerfRequests</b> member.</p>
</dd>

### -field PerfRequests

<dd>
<p>[in] A pointer to an array of <a href="..\pepfx\ns-pepfx--pep-component-perf-state-request.md">PEP_COMPONENT_PERF_STATE_REQUEST</a> structures. Each element in the array specifies a new performance level to assign to a P-state set. The number of array elements is specified by the <b>PerfRequestsCount</b> member.</p>
</dd>
</dl>

## -remarks
<p>This structure is used by the <a href="kernel.pep_dpm_request_component_perf_state">PEP_DPM_REQUEST_COMPONENT_PERF_STATE</a> notification. The <b>DeviceHandle</b>, <b>Component</b>, <b>PerfRequestsCount</b>, and <b>PerfRequests</b> members of the structure contain input values that are supplied by PoFx when this notification is sent. The <b>Completed</b> and <b>Succeeded</b> members contain output values that the PEP writes to the structure in response to the notification.</p>

<p>The PEP can complete the requested P-state changes either synchronously or asynchronously. The PEP can set the <b>Completed</b> member to TRUE to indicate that all the requests in the <b>PEP_DPM_REQUEST_COMPONENT_PERF_STATE</b> notification have been completed synchronously—that is, before the return from the PEP's <a href="kernel.acceptdevicenotification">AcceptDeviceNotification</a> callback routine. Or, the PEP can set <b>Completed</b> to FALSE to indicate that the requests will be completed asynchronously. To complete the requests asynchronously, the PEP should call the <a href="kernel.requestworker">RequestWorker</a> routine to inform PoFx that the PEP has a work request to submit, and PoFx will respond by sending a <a href="kernel.pep_dpm_work">PEP_DPM_WORK</a> notification to the PEP.</p>

<p>PoFx writes the requested P-state changes to the <b>PerfRequests</b> array before the <b>PEP_DPM_REQUEST_COMPONENT_PERF_STATE</b> notification is sent. If the PEP handles the requested P-state changes <i>synchronously</i>, the contents of the <b>PerfRequests</b> array remain valid only until the return from the <i>AcceptDeviceNotification</i> callback routine. If the requests are completed <i>asynchronously</i>,  the array contents remain valid until the PEP calls the <a href="kernel.completework">CompleteWork</a> routine to notify PoFx that the PEP has completed the pending requests.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 10.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="kernel.acceptdevicenotification">AcceptDeviceNotification</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx--pep-component-perf-state-request.md">PEP_COMPONENT_PERF_STATE_REQUEST</a>
</dt>
<dt>
<a href="..\pepfx\ns-pepfx--pep-device-register-v2.md">PEP_DEVICE_REGISTER_V2</a>
</dt>
<dt>
<a href="kernel.pep_dpm_register_device">PEP_DPM_REGISTER_DEVICE</a>
</dt>
<dt>
<a href="kernel.pep_dpm_request_component_perf_state">PEP_DPM_REQUEST_COMPONENT_PERF_STATE</a>
</dt>
<dt>
<a href="kernel.pep_dpm_work">PEP_DPM_WORK</a>
</dt>
<dt>
<a href="kernel.requestworker">RequestWorker</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_REQUEST_COMPONENT_PERF_STATE structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
