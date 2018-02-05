---
UID : NI:ntddstor.IOCTL_STORAGE_PERSISTENT_RESERVE_IN
title : IOCTL_STORAGE_PERSISTENT_RESERVE_IN
author : windows-driver-content
description : The generic storage class driver (classpnp.sys) exposes an I/O control (IOCTL) interface for issuing Persistent Reserve In commands.
old-location : storage\ioctl_storage_persistent_reserve_in.htm
old-project : storage
ms.assetid : a5a3e98b-8f6b-412d-a2eb-a28b5664340d
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_storage_persistent_reserve_in, IOCTL_STORAGE_PERSISTENT_RESERVE_IN control code [Storage Devices], IOCTL_STORAGE_PERSISTENT_RESERVE_IN, ntddstor/IOCTL_STORAGE_PERSISTENT_RESERVE_IN, k307_d142d4f6-d2a1-420e-a41d-5bb630445ad2.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddstor.h
req.include-header : Ntddstor.h
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_PERSISTENT_RESERVE_IN IOCTL
The generic storage class driver (<i>classpnp.sys</i>) exposes an I/O control (IOCTL) interface for issuing Persistent Reserve In commands. The behavior of the storage device when a Persistent Reserve In command is received is described in the <a href="http://go.microsoft.com/fwlink/p/?linkid=153142">SCSI Primary Commands - 2 (SPC-2)</a> specification. The IOCTL interface requires the caller to have read access to the physical device for Persistent Reserve In commands. User-mode applications, services, and kernel-mode drivers can use this IOCTL to control persistent reservations. If called from a driver, this IOCTL must be called from a thread running at IRQL &lt; DISPATCH_LEVEL. This IOCTL is defined with FILE_READ_ACCESS, requiring a device handle to have read permissions to issue the Persistent Reserve In command.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddstor\ns-ntddstor-_persistent_reserve_command.md">PERSISTENT_RESERVE_COMMAND</a> structure. You must allocate the buffer from nonpaged pool and must align it correctly for the  target device and adapter.

PR_IN.ServiceAction can be one of the following:
<ul>
<li>
RESERVATION_ACTION_READ_KEYS

</li>
<li>
RESERVATION_ACTION_READ_RESERVATIONS

</li>
</ul>PR_IN.Allocation length is the size (in bytes) of the buffer allocated for the returned parameter list.

### Input Buffer Length
The length of .

### Output Buffer
For PR_IN.ServiceAction = RESERVATION_ACTION_READ_KEYS, the output buffer contains a <a href="..\storport\ns-storport-pri_registration_list.md">PRI_REGISTRATION_LIST</a> structure and must be at least sizeof(PRI_REGISTRATION_LIST).

For PR_IN.ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS, the output buffer contains a <a href="..\storport\ns-storport-pri_reservation_list.md">PRI_RESERVATION_LIST</a> structure and must be at least sizeof(PRI_RESERVATION_LIST).

If the allocated buffer is too small to return all the Persistent Reserve In data, success will be returned and the required size will be returned in the parameter list <b>AdditionalLength</b> field.

### Output Buffer Length
The length of .

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the size of the output buffer. For ServiceAction = RESERVATION_ACTION_READ_KEYS, the output buffer is a <a href="..\storport\ns-storport-pri_registration_list.md">PRI_REGISTRATION_LIST</a> structure. For ServiceAction = RESERVATION_ACTION_READ_RESERVATIONS, the output buffer is a <a href="..\storport\ns-storport-pri_reservation_list.md">PRI_RESERVATION_LIST</a> structure.

The <b>Status</b> field is set to one of the following:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |