---
UID: NI:ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT
author: windows-driver-content
description: Sets the TRANSMIT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.
old-location: buses\ioctl_ucmtcpci_port_controller_set_transmit.htm
old-project: usbref
ms.assetid: 5E833F26-2BEC-4021-8D19-F9EFD49C7584
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ioctl_ucmtcpci_port_controller_set_transmit, IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT control code [Buses], IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT, ucmtcpciportcontrollerrequests/IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	UcmTcpciPortControllerRequests.h
apiname:
-	IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_IOCTL
req.product: Windows 10 or later.
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT IOCTL
Sets the TRANSMIT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A pointer to a <a href="..\ucmtcpciportcontrollerrequests\ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_transmit_in_params.md">UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS</a> structure that contains the value to set in the TRANSMIT Register. To get the structure, call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestretrieveinputbuffer.md">WdfRequestRetrieveInputBuffer</a> by passing the received framework request object. This structure is declared in UcmTcpciSpec.h.

### Input Buffer Length
The size of the <a href="..\ucmtcpciportcontrollerrequests\ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_transmit_in_params.md">UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS</a> structure.

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
The UcmTcpciCx class extension sends this IOCTL request to set the TRANSMIT Register. The value to set is provided in the supplied structure. After setting the value in the register, client driver must call <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> to complete the request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucmtcpciportcontrollerrequests.h |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>