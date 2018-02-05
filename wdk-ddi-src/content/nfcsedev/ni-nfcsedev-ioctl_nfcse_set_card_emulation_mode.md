---
UID : NI:nfcsedev.IOCTL_NFCSE_SET_CARD_EMULATION_MODE
title : IOCTL_NFCSE_SET_CARD_EMULATION_MODE
author : windows-driver-content
description : The IOCTL_NFCSE_SET_CARD_EMULATION_MODE control code sets whether the specified secure element is exposed in card emulation mode.
old-location : nfpdrivers\ioctl_nfcse_set_card_emulation_mode.htm
old-project : nfpdrivers
ms.assetid : B7E55FDE-573C-4F45-869C-A3EE253BD777
ms.author : windowsdriverdev
ms.date : 12/18/2017
ms.keywords : nfpdrivers.ioctl_nfcse_set_card_emulation_mode, IOCTL_NFCSE_SET_CARD_EMULATION_MODE control code [Near-Field Proximity Drivers], IOCTL_NFCSE_SET_CARD_EMULATION_MODE, nfcsedev/IOCTL_NFCSE_SET_CARD_EMULATION_MODE
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
req.typenames : "*PSECURE_ELEMENT_TYPE, SECURE_ELEMENT_TYPE"
---

# IOCTL_NFCSE_SET_CARD_EMULATION_MODE IOCTL
The <b>IOCTL_NFCSE_SET_CARD_EMULATION_MODE</b> 
   control code sets whether the specified secure element is exposed in card emulation mode. When a secure element is “exposed” as card emulation, it means when the device is brought to an external reader that secure element can be accessed by the reader. The IOCTL is issued on a file handle opened with a relative filename ‘SEManage’. The driver MUST grant exclusive access to the client to manage card emulation mode, that is, subsequent calls to open a file handle using relative filename ‘SEManage’ will fail with STATUS_ACCCESS_DENIED until the client with exclusive access closes its file handle.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<a href="..\nfcsedev\ns-nfcsedev-_secure_element_set_card_emulation_mode_info.md"> SECURE_ELEMENT_SET_CARD_EMULATION_MODE_INFO</a> structure.

### Input Buffer Length
<text></text>

### Output Buffer
None

### Output Buffer Length
<text></text>

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
<td>If the secure element GUID is invalid or output buffer is non-zero.</td>
</tr>
<tr>
<td><b>STATUS_INVALID_DEVICE_STATE</b></td>
<td>  If the IOCTL is sent on a handle other than with the relative name 'SEManage'.</td>
</tr>
</table>

## Remarks
The following are requirements that the driver must adhere to. <ul>
<li>This IOCTL must be called on a handle that has an SEEvents relative file name; otherwise, the driver returns STATUS_INVALID_DEVICE_STATE.</li>
<li>If card emulation mode is set to EmulationOff for all the secure elements that are attached to the NFC controller, the emulation mode of the polling loop must be disabled. If proximity features are also disabled, the driver should transition to a low power mode.</li>
<li>If card emulation mode is set to a value other than EmulationOff, then the driver must continue to be in the D0 state and the emulation mode of the polling loop should be enabled (detectable to external readers).</li>
<li>When the SEManage opened file handle is closed, the driver must set the card emulation mode settings of all secure elements to be EmulationOff except when the last set card emulation mode state is EmulationOnPowerIndependent. If the last set card emulation mode state is EmulationOnPowerIndependent, the driver must remain with the card emulation mode setting to On with the PbF option for the specific secure elements.</li>
<li>The driver must grant exclusive access to the client to manage card emulation mode. Subsequent calls to open a file handle using relative filename SEManage would fail with STATUS_ACCCESS_DENIED until the client with exclusive access closes its file handle.</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | nfcsedev.h |