---
UID: NI.ucmtcpciportcontrollerrequests.IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL
title: IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL
author: windows-driver-content
description: Gets the values of all control registers defined as per the Universal Serial Bus Type-C Port Controller Interface Specification.
old-location: buses\ioctl_ucmtcpci_port_controller_get_control.htm
old-project: usbref
ms.assetid: A7C405C1-D059-41A6-8A3B-B3D2EBACE22D
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION, *PUCMTCPCI_PORT_CONTROLLER_IDENTIFICATION
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
req.alt-api: IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL
req.alt-loc: UcmTcpciPortControllerRequests.h
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
req.iface: 
req.product: Windows 10 or later.
---

# IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL IOCTL



## -description
<p>Gets the values of all control registers defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. </p>


## -ioctlparameters

### -input-buffer
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt805875">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS</a> structure that contains all control register values. To get the structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550014">WdfRequestRetrieveInputBuffer</a> by passing the received framework request object.</p>

<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt805875">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS</a> structure that contains all control register values. To get the structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550014">WdfRequestRetrieveInputBuffer</a> by passing the received framework request object.</p>

### -input-buffer-length
<p>The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805875">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS</a> structure.</p>

<p>The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805875">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS</a> structure.</p>

<p>The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805875">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS</a> structure.</p>

### -output-buffer
<p>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure. To get the structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550018">WdfRequestRetrieveOutputBuffer</a> by passing the received framework request object.</p>

<p>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure. To get the structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550018">WdfRequestRetrieveOutputBuffer</a> by passing the received framework request object.</p>

<p>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure. To get the structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550018">WdfRequestRetrieveOutputBuffer</a> by passing the received framework request object.</p>

<p>A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure. To get the structure, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550018">WdfRequestRetrieveOutputBuffer</a> by passing the received framework request object.</p>

### -output-buffer-length
<p>The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure.</p>

<p>The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure.</p>

<p>The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure.</p>

<p>The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure.</p>

<p>The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure.</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. </p>

## -remarks
<p>The UcmTcpciCx class extension sends this IOCTL request to retrieve the values of the control registers. The client driver must communicate with the port controller to retrieve the POWER_CONTROL, ROLE_CONTROL, TCPC_CONTROL, and FAULT_CONTROL Register values and populate the received  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure with those values. To complete the request, the driver must set the populated structure on the framework request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a> and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.</p>

<p>The UcmTcpciCx class extension sends this IOCTL request to retrieve the values of the control registers. The client driver must communicate with the port controller to retrieve the POWER_CONTROL, ROLE_CONTROL, TCPC_CONTROL, and FAULT_CONTROL Register values and populate the received  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure with those values. To complete the request, the driver must set the populated structure on the framework request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a> and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.</p>

<p>The UcmTcpciCx class extension sends this IOCTL request to retrieve the values of the control registers. The client driver must communicate with the port controller to retrieve the POWER_CONTROL, ROLE_CONTROL, TCPC_CONTROL, and FAULT_CONTROL Register values and populate the received  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure with those values. To complete the request, the driver must set the populated structure on the framework request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a> and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.</p>

<p>The UcmTcpciCx class extension sends this IOCTL request to retrieve the values of the control registers. The client driver must communicate with the port controller to retrieve the POWER_CONTROL, ROLE_CONTROL, TCPC_CONTROL, and FAULT_CONTROL Register values and populate the received  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure with those values. To complete the request, the driver must set the populated structure on the framework request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a> and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.</p>

<p>The UcmTcpciCx class extension sends this IOCTL request to retrieve the values of the control registers. The client driver must communicate with the port controller to retrieve the POWER_CONTROL, ROLE_CONTROL, TCPC_CONTROL, and FAULT_CONTROL Register values and populate the received  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure with those values. To complete the request, the driver must set the populated structure on the framework request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a> and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.</p>

<p>The UcmTcpciCx class extension sends this IOCTL request to retrieve the values of the control registers. The client driver must communicate with the port controller to retrieve the POWER_CONTROL, ROLE_CONTROL, TCPC_CONTROL, and FAULT_CONTROL Register values and populate the received  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure with those values. To complete the request, the driver must set the populated structure on the framework request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a> and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.</p>

<p>The UcmTcpciCx class extension sends this IOCTL request to retrieve the values of the control registers. The client driver must communicate with the port controller to retrieve the POWER_CONTROL, ROLE_CONTROL, TCPC_CONTROL, and FAULT_CONTROL Register values and populate the received  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805876">UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS</a> structure with those values. To complete the request, the driver must set the populated structure on the framework request object by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff550032">WdfRequestSetInformation</a> and then call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> to complete the request.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>UcmTcpciPortControllerRequests.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL control code%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
