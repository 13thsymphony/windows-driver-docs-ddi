---
UID : NI:nfcsedev.IOCTL_NFCSE_HCE_REMOTE_SEND
title : IOCTL_NFCSE_HCE_REMOTE_SEND
author : windows-driver-content
description : Transmits response APDU from DeviceHost NFCEE to remote device. The caller must be sure that response APDU is conformant to ISO-IEC 7816-4.
old-location : nfpdrivers\ioctl_nfcse_hce_remote_send.htm
old-project : nfpdrivers
ms.assetid : 5BA627C9-747D-493A-B568-B2912BBB622F
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : _SECURE_ELEMENT_TYPE, *PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : nfcsedev.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_NFCSE_HCE_REMOTE_SEND
req.alt-loc : nfcsedev.h
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
req.typenames : "*PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE"
---

# IOCTL_NFCSE_HCE_REMOTE_SEND IOCTL
Transmits response APDU from DeviceHost NFCEE to remote device. The caller must be sure that response APDU is conformant to ISO-IEC 7816-4.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Pointer to buffer containing <a href="..\nfcsedev\ns-nfcsedev-_secure_element_hce_data_packet.md">SECURE_ELEMENT_HCE_DATA_PACKET</a> structure.

### Input Buffer Length
sizeof(SECURE_ELEMENT_HCE_DATA_PACKET)

### Output Buffer
None

### Output Buffer Length
None

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | nfcsedev.h |
| **IRQL** |  |