---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL
author: windows-driver-content
description: Gets the values of all control registers defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.
old-location: buses\ioctl_ucmtcpci_port_controller_get_control.htm
old-project: usbref
ms.assetid: A7C405C1-D059-41A6-8A3B-B3D2EBACE22D
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL, IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL control code [Buses], buses.ioctl_ucmtcpci_port_controller_get_control, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL
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
-	IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_IOCTL
req.product: Windows 10 or later.
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL IOCTL
Gets the values of all control registers defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt805875">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS</a> structure that contains all control register values. To get the structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550014">WdfRequestRetrieveInputBuffer</a> by passing the received framework request object.

### Input Buffer Length
The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805875">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS</a> structure.

### Output Buffer
A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure. To get the structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550018">WdfRequestRetrieveOutputBuffer</a> by passing the received framework request object.

### Output Buffer Length
The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
The UcmTcpciCx class extension sends this IOCTL request to retrieve the values of the control registers. The client driver must communicate with the port controller to retrieve the POWER_CONTROL, ROLE_CONTROL, TCPC_CONTROL, and FAULT_CONTROL Register values and populate the received  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure with those values. To complete the request, the driver must set the populated structure on the framework request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a> and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontrollerrequests.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>