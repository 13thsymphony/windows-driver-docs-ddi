---
UID : NI:ntddcdvd.IOCTL_AACS_READ_BINDING_NONCE
title : IOCTL_AACS_READ_BINDING_NONCE
author : windows-driver-content
description : Reads the Advanced Access Content System (AACS) binding nonce starting at the specified byte offset on the disc, as part of the protocol for reading a protected data area.
old-location : storage\ioctl_aacs_read_binding_nonce.htm
old-project : storage
ms.assetid : d90ce010-a2c6-43e8-8bf8-750af5b784ba
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_aacs_read_binding_nonce, IOCTL_AACS_READ_BINDING_NONCE control code [Storage Devices], IOCTL_AACS_READ_BINDING_NONCE, ntddcdvd/IOCTL_AACS_READ_BINDING_NONCE, k307_5a403ffd-678e-44e7-8df3-21e3149b7efd.xml
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

# IOCTL_AACS_READ_BINDING_NONCE IOCTL
Reads the Advanced Access Content System (AACS) binding nonce starting at the specified byte offset on the disc, as part of the protocol for reading a protected data area.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a structure of type <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_read_binding_nonce.md">AACS_READ_BINDING_NONCE</a> that specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a>, the starting logical block address and the number of sectors for which the logical unit should generate a binding nonce.

### Input Buffer Length
Length of a <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_read_binding_nonce.md">AACS_READ_BINDING_NONCE</a> structure.

### Output Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the value of type <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_binding_nonce.md">AACS_BINDING_NONCE</a> that specifies the binding nonce.

### Output Buffer Length
Length of a <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_read_binding_nonce.md">AACS_READ_BINDING_NONCE</a> structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.

## Remarks
The IOCTL_AACS_READ_BINDING_NONCE request corresponds to the part of the AACS authentication protocol that is responsible for reading a protected data area. For a complete description of this protocol, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).

The AGID is automatically released after the IOCTL_AACS_READ_BINDING_NONCE request completes.

Clients that do not use file system support must set the <b>Handle</b> member of <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_read_binding_nonce.md">AACS_READ_BINDING_NONCE</a> to INVALID_HANDLE_VALUE and specify explicit values for the <b>StartLBA</b> and <b>NumberOfSectors</b> members.

When the CDROM driver receives the IOCTL, it will fail the IOCTL immediately with STATUS_INVALID_PARAMETER if either the <b>StartLBA</b> field is set to MAXULONGLONG or the <b>NumberOfSectors</b> field is set to MAXULONG.  In this case,  the caller should release the AGID manually.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |
| **IRQL** |  |