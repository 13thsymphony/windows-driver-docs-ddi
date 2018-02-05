---
UID : NI:ntddcdvd.IOCTL_AACS_START_SESSION
title : IOCTL_AACS_START_SESSION
author : windows-driver-content
description : Retrieves an Authentication Grant Identifier (AGID) that identifies a secure session.
old-location : storage\ioctl_aacs_start_session.htm
old-project : storage
ms.assetid : b5fb5dac-7f63-4457-bb25-61315395429b
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_aacs_start_session, IOCTL_AACS_START_SESSION control code [Storage Devices], IOCTL_AACS_START_SESSION, ntddcdvd/IOCTL_AACS_START_SESSION, k307_a9378e49-2d39-4532-bac7-5fe9612ea5d0.xml
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

# IOCTL_AACS_START_SESSION IOCTL
Retrieves an Authentication Grant Identifier (AGID) that identifies a secure session.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID). The AGID identifies the secure session.

### Output Buffer Length
Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.

## Remarks
The IOCTL_AACS_START_SESSION request corresponds to one of the steps of the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth). For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).

After obtaining the AGID, host software uses the AGID to associate subsequent AACS IOCTLs with the secure session. Unlike the AGID that is used with DVD Content-Scrambling System (CSS) encryption, the AACS AGID is valid for the transfer of only one piece of protected information.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |