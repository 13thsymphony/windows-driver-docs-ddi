---
UID: NI:ntddcdvd.IOCTL_AACS_READ_MEDIA_KEY_BLOCK
title: IOCTL_AACS_READ_MEDIA_KEY_BLOCK
author: windows-driver-content
description: Queries the logical unit for the Media Key Block (MKB).
old-location: storage\ioctl_aacs_read_media_key_block.htm
old-project: storage
ms.assetid: 08852f41-1836-4c55-bf6f-0246caa2c8bd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_aacs_read_media_key_block, IOCTL_AACS_READ_MEDIA_KEY_BLOCK control code [Storage Devices], IOCTL_AACS_READ_MEDIA_KEY_BLOCK, ntddcdvd/IOCTL_AACS_READ_MEDIA_KEY_BLOCK, k307_0e90884e-4c78-4fd5-b30c-eed14d73ba5e.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddcdvd.h
apiname:
-	IOCTL_AACS_READ_MEDIA_KEY_BLOCK
product: Windows
targetos: Windows
req.typenames: "*PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT"
---

# IOCTL_AACS_READ_MEDIA_KEY_BLOCK IOCTL
Queries the logical unit for the Media Key Block (MKB).

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the AACS_LAYER_NUMBER number of the layer. The AACS_LAYER_NUMBER is an unsigned long integer value in the range 0 to 255 inclusive that specifies the layer of the media to which a command applies.

<code>typedef ULONG AACS_LAYER_NUMBER, *PAACS_LAYER_NUMBER;
</code>

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the buffer, which must be &gt;= <b>sizeof</b>(AACS_LAYER_NUMBER).

### Output Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an opaque, variable-length MKB. The size of the MKB is always a multiple of 32,768 (0x8000).

### Output Buffer Length
Length of a variable-length MKB.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS if the operation succeeds. If <b>Irp-&gt;AssociatedIrp.SystemBuffer </b>is <b>NULL</b> or the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> is not sufficient to contain the full MKB, the operation fails and returns a status of STATUS_BUFFER_TOO_SMALL, and the required buffer size is returned in <b>IoStatus.Information</b>.

## Remarks
The storage stack uses a READ DISC STRUCTURE command (format 0x17) with Advanced Access Control System (AACS) extensions to retrieve the MKB. IOCTL_AACS_READ_MEDIA_KEY_BLOCK request will not work if the media in the logical unit is not AACS protected. 

Unlike the MKB that is used with Content-Scrambling System (CSS) encryption, AACS MKBs are self-protected with digital signatures. The MKB structure is fully documented in the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).

The IOCTL_AACS_READ_MEDIA_KEY_BLOCK request corresponds to one of the steps of the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth). For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdvd.h (include Ntddcdvd.h) |