---
UID: NI.gnssdriver.IOCTL_GNSS_LISTEN_ERROR
title: IOCTL_GNSS_LISTEN_ERROR
author: windows-driver-content
description: The IOCTL_GNSS_LISTEN_ERROR control code is used to start listening for ERROR events from the driver.
old-location: sensors\ioctl_gnss_listen_error_.htm
old-project: sensors
ms.assetid: 4B08FB8D-8C4A-4C23-A809-11E7DF190236
ms.author: windowsdriverdev
ms.date: 11/26/2017
ms.keywords: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_, FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_GNSS_LISTEN_ERROR
req.alt-loc: gnssdriver.h
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
---

# IOCTL_GNSS_LISTEN_ERROR IOCTL



## -description
<p>The <b>IOCTL_GNSS_LISTEN_ERROR</b>
   control code is used to start listening for ERROR events from the driver.</p>


## -ioctlparameters

### -input-buffer
<p>Set to NULL.</p>

### -input-buffer-length
<p>Set to 0.</p>

<p>Set to 0.</p>

### -output-buffer
<p>A pointer to a GNSS_EVENT structure.</p>

<p>The EventType must be set to GNSS_Event_Error and the ErrorCode, IsRecoverable and ErrorDescription members of ErrorInformation filled in.</p>

<p>A pointer to a GNSS_EVENT structure.</p>

<p>The EventType must be set to GNSS_Event_Error and the ErrorCode, IsRecoverable and ErrorDescription members of ErrorInformation filled in.</p>

<p>A pointer to a GNSS_EVENT structure.</p>

<p>The EventType must be set to GNSS_Event_Error and the ErrorCode, IsRecoverable and ErrorDescription members of ErrorInformation filled in.</p>

### -output-buffer-length
<p>Set to 0.</p>

<p>Set to 0.</p>

<p>Set to 0.</p>

<p>Set to 0.</p>

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

## -remarks
<p>The GNSS adapter ensures that this request is always pending, so that the driver can indicate an error.

</p>

<p>When the driver completes the I/O call, the adapter issues another IOCTL to continue waiting for further error notifications.</p>

<p>The driver can complete this call when it wants to report an error condition. The GNSS adapter will use the error data to log telemetry events.

</p>

<p>The Error code is in HRESULT format. The driver can create codes using the <b>MAKE_HRESULT</b> macro with codes in <b>FACILITY_ITF</b>.</p>

<p>The GNSS adapter ensures that this request is always pending, so that the driver can indicate an error.

</p>

<p>When the driver completes the I/O call, the adapter issues another IOCTL to continue waiting for further error notifications.</p>

<p>The driver can complete this call when it wants to report an error condition. The GNSS adapter will use the error data to log telemetry events.

</p>

<p>The Error code is in HRESULT format. The driver can create codes using the <b>MAKE_HRESULT</b> macro with codes in <b>FACILITY_ITF</b>.</p>

<p>The GNSS adapter ensures that this request is always pending, so that the driver can indicate an error.

</p>

<p>When the driver completes the I/O call, the adapter issues another IOCTL to continue waiting for further error notifications.</p>

<p>The driver can complete this call when it wants to report an error condition. The GNSS adapter will use the error data to log telemetry events.

</p>

<p>The Error code is in HRESULT format. The driver can create codes using the <b>MAKE_HRESULT</b> macro with codes in <b>FACILITY_ITF</b>.</p>

<p>The GNSS adapter ensures that this request is always pending, so that the driver can indicate an error.

</p>

<p>When the driver completes the I/O call, the adapter issues another IOCTL to continue waiting for further error notifications.</p>

<p>The driver can complete this call when it wants to report an error condition. The GNSS adapter will use the error data to log telemetry events.

</p>

<p>The Error code is in HRESULT format. The driver can create codes using the <b>MAKE_HRESULT</b> macro with codes in <b>FACILITY_ITF</b>.</p>

<p>The GNSS adapter ensures that this request is always pending, so that the driver can indicate an error.

</p>

<p>When the driver completes the I/O call, the adapter issues another IOCTL to continue waiting for further error notifications.</p>

<p>The driver can complete this call when it wants to report an error condition. The GNSS adapter will use the error data to log telemetry events.

</p>

<p>The Error code is in HRESULT format. The driver can create codes using the <b>MAKE_HRESULT</b> macro with codes in <b>FACILITY_ITF</b>.</p>

<p>The GNSS adapter ensures that this request is always pending, so that the driver can indicate an error.

</p>

<p>When the driver completes the I/O call, the adapter issues another IOCTL to continue waiting for further error notifications.</p>

<p>The driver can complete this call when it wants to report an error condition. The GNSS adapter will use the error data to log telemetry events.

</p>

<p>The Error code is in HRESULT format. The driver can create codes using the <b>MAKE_HRESULT</b> macro with codes in <b>FACILITY_ITF</b>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_LISTEN_ERROR control code%20 RELEASE:%20(11/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
