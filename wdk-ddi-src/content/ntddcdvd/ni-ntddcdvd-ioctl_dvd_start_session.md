---
UID : NI:ntddcdvd.IOCTL_DVD_START_SESSION
title : IOCTL_DVD_START_SESSION
author : windows-driver-content
description : Returns an authentication grant ID (AGID) as a DVD session ID, which a caller must pass to the device in all subsequent operations in a DVD session.
old-location : storage\ioctl_dvd_start_session.htm
old-project : storage
ms.assetid : a4010756-b230-4e49-85a4-498f5ebcf785
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_dvd_start_session, IOCTL_DVD_START_SESSION control code [Storage Devices], IOCTL_DVD_START_SESSION, ntddcdvd/IOCTL_DVD_START_SESSION, k307_e26336f9-b482-4340-8315-cd8771c5bb81.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddcdvd.h
req.include-header : Ntddcdvd.h
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
req.typenames : DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT
---

# IOCTL_DVD_START_SESSION IOCTL
Returns an authentication grant ID (AGID) as a DVD session ID, which a caller must pass to the device in all subsequent operations in a DVD session.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The driver returns an integer authentication grant ID of type DVD_SESSION_ID in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to <b>sizeof</b>(DVD_SESSION_ID). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |