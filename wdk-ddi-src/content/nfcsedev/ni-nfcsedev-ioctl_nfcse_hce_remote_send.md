---
UID: NI:nfcsedev.IOCTL_NFCSE_HCE_REMOTE_SEND
title: IOCTL_NFCSE_HCE_REMOTE_SEND
author: windows-driver-content
description: Transmits response APDU from DeviceHost NFCEE to remote device. The caller must be sure that response APDU is conformant to ISO-IEC 7816-4.
old-location: nfpdrivers\ioctl_nfcse_hce_remote_send.htm
old-project: nfpdrivers
ms.assetid: 5BA627C9-747D-493A-B568-B2912BBB622F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: nfpdrivers.ioctl_nfcse_hce_remote_send, IOCTL_NFCSE_HCE_REMOTE_SEND, IOCTL_NFCSE_HCE_REMOTE_SEND control code [Near-Field Proximity Drivers], IOCTL_NFCSE_HCE_REMOTE_SEND, nfcsedev/IOCTL_NFCSE_HCE_REMOTE_SEND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: nfcsedev.h
req.include-header: 
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
-	nfcsedev.h
apiname:
-	IOCTL_NFCSE_HCE_REMOTE_SEND
product: Windows
targetos: Windows
req.typenames: "*PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE"
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
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

<table>
<tr>
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td><b>STATUS_INVALID_PARAMETER</b></td>
<td>This code is returned if the input connection ID does not match the current connection ID.</td>
</tr>
<tr>
<td><b>STATUS_INVALID_DEVICE_STATE</b></td>
<td> This code is returned if the IOCTL is sent on a handle other than with relative name ‘SEManage’.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | nfcsedev.h |