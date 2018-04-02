---
UID: NI:ntddcdvd.IOCTL_AACS_SEND_CERTIFICATE
title: IOCTL_AACS_SEND_CERTIFICATE
author: windows-driver-content
description: Sends the host certificate to the logical unit.
old-location: storage\ioctl_aacs_send_certificate.htm
old-project: storage
ms.assetid: e56b2d31-cb59-489d-ab12-7657406ba67a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_AACS_SEND_CERTIFICATE, IOCTL_AACS_SEND_CERTIFICATE control code [Storage Devices], k307_c275c772-8b16-4397-ba4d-3ff3ebc5eb40.xml, ntddcdvd/IOCTL_AACS_SEND_CERTIFICATE, storage.ioctl_aacs_send_certificate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddcdvd.h
api_name:
-	IOCTL_AACS_SEND_CERTIFICATE
product:
- Windows
targetos: Windows
req.typenames: DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT
---

# IOCTL_AACS_SEND_CERTIFICATE IOCTL
Sends the host certificate to the logical unit.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains host certificate of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff550113">AACS_SEND_CERTIFICATE</a>.

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(AACS_SEND_CERTIFICATE).

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(AACS_SEND_CERTIFICATE).

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.

## Remarks
The IOCTL_AACS_SEND_CERTIFICATE request corresponds to the step in the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth) in which the host sends its certificate and nonce to the drive. For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |