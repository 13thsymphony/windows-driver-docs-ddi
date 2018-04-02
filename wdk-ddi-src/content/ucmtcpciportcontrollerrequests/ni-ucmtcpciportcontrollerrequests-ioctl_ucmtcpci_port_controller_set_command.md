---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND
author: windows-driver-content
description: Sets the value of a command register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.
old-location: buses\ioctl_ucmtcpci_port_controller_set_command.htm
old-project: usbref
ms.assetid: 0E481454-583C-4E2B-B4F2-C9E72B1D3DCC
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND control code [Buses], buses.ioctl_ucmtcpci_port_controller_set_command, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ucmtcpciportcontrollerrequests.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UcmTcpciPortControllerRequests.h
api_name:
-	IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_IOCTL
req.product: Windows 10 or later.
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND IOCTL
Sets the value of a command register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt805881">UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS</a> structure. To get the structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550014">WdfRequestRetrieveInputBuffer</a> by passing the received framework request object.

### Input Buffer Length
The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805881">UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS</a> structure.

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
The UcmTcpciCx class extension sends this IOCTL request to set the value of the command register. The value to set is provided in the supplied structure. After setting the value in the register, client driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontrollerrequests.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>