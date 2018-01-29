---
UID : NI:pcivirt.IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
title : IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
author : windows-driver-content
description : The IOCTL_SRIOV_MITIGATED_RANGE_UPDATE request indicates that the virtualization stack wants to update to the mitigation ranges.
old-location : pci\ioctl-sriov-mitigated-range-update.htm
old-project : PCI
ms.assetid : f49e6d9e-0b62-4742-9868-1717f8482d9a
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : PCI.ioctl-sriov-mitigated-range-update, IOCTL_SRIOV_MITIGATED_RANGE_UPDATE control code [Buses], IOCTL_SRIOV_MITIGATED_RANGE_UPDATE, pcivirt/IOCTL_SRIOV_MITIGATED_RANGE_UPDATE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : pcivirt.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSRIOV_PF_EVENT, SRIOV_PF_EVENT"
---

# IOCTL_SRIOV_MITIGATED_RANGE_UPDATE IOCTL
The  <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request indicates that the virtualization stack wants to update to the mitigation ranges.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A pointer to a <a href="https://msdn.microsoft.com/ae4936ac-9794-4854-81ec-2139b3ce4c3c">SRIOV_MITIGATED_RANGE_UPDATE_INPUT</a> structure

### Input Buffer Length
<text></text>

### Output Buffer
<text></text>

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
This IOCTL request is sent by the virtualization stack to the  PCI Express SR-IOV Physical Function (PF) driver that exposes GUID_DEVINTERFACE_VIRTUALIZABLE_DEVICE.

The stack uses an I/O MMU to differentiate traffic coming from the various interfaces that the device exposes, enforcing policy about which regions of memory a device can access and which interrupts it can generate. When that range of memory is updated, the stack sends this request.

The physical function (PF driver) keeps the <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request in its queue until the request is either cancelled by the virtualization stack or the PF driver
wants to send a request to the virtual function (VF) driver to update to the mitigation ranges for 
a particular VF.  When the VF completes the request, the PF completes the <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request.  Upon completion, the virtualization stack reinitializes the mitigation
maps by sending <a href="https://msdn.microsoft.com/68fd97a5-b7ea-43c0-96ed-b64445fd21dd">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a> and
<a href="https://msdn.microsoft.com/58b6e53d-be7a-4563-a27d-db216a12d60d">IOCTL_SRIOV_QUERY_MITIGATED_RANGES</a> requests.  The stack may additionally  call any
user mode device simulation for additional ranges to mitigate. The <b>IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</b> request is sent for each active virtual function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | pcivirt.h |
| **IRQL** | PASSIVE_LEVEL |