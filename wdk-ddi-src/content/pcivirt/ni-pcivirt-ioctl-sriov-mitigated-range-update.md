---
UID: NI.pcivirt.IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
title: IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
author: windows-driver-content
description: The IOCTL_SRIOV_MITIGATED_RANGE_UPDATE request indicates that the virtualization stack wants to update to the mitigation ranges.
old-location: pci\ioctl-sriov-mitigated-range-update.htm
old-project: PCI
ms.assetid: f49e6d9e-0b62-4742-9868-1717f8482d9a
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PARCLASS_INFORMATION, PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
req.alt-loc: Pcivirt.h
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

# IOCTL_SRIOV_MITIGATED_RANGE_UPDATE IOCTL



## -description
<p>The  <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request indicates that the virtualization stack wants to update to the mitigation ranges.</p>


## -ioctlparameters

### -input-buffer
<p>A pointer to a <a href="buses._sriov_mitigated_range_update_input">SRIOV_MITIGATED_RANGE_UPDATE_INPUT</a> structure</p>

<p>A pointer to a <a href="buses._sriov_mitigated_range_update_input">SRIOV_MITIGATED_RANGE_UPDATE_INPUT</a> structure</p>

### -input-buffer-length

<text></text>

### -output-buffer

<text></text>

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

## -remarks
<p>This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.</p>

<p>The stack uses an I/O MMU to differentiate traffic coming from the various interfaces that the device exposes, enforcing policy about which regions of memory a device can access and which interrupts it can generate. When that range of memory is updated, the stack sends this request.</p>

<p>The physical function (PF driver) keeps the <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request in its queue until the request is either cancelled by the virtualization stack or the PF driver
wants to send a request to the virtual function (VF) driver to update to the mitigation ranges for 
a particular VF.  When the VF completes the request, the PF completes the <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request.  Upon completion, the virtualization stack reinitializes the mitigation
maps by sending <a href="buses.ioctl_sriov_query_mitigated_range_count">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a> and
<a href="buses.ioctl_sriov_query_mitigated_ranges">IOCTL_SRIOV_QUERY_MITIGATED_RANGES</a> requests.  The stack may additionally  call any
user mode device simulation for additional ranges to mitigate. The <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request is sent for each active virtual function.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pcivirt.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>