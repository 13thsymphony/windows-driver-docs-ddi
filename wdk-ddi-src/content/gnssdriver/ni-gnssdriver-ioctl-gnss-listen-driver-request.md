---
UID: NI.gnssdriver.IOCTL_GNSS_LISTEN_DRIVER_REQUEST
title: IOCTL_GNSS_LISTEN_DRIVER_REQUEST
author: windows-driver-content
description: The IOCTL_GNSS_LISTEN_DRIVER_REQUEST control code is used by the GNSS driver to get data from the HLOS.
old-location: sensors\ioctl_gnss_listen_driver_request.htm
old-project: sensors
ms.assetid: 204D6F80-A458-45F8-B25F-4F5D3C33EB75
ms.author: windowsdriverdev
ms.date: 11/30/2017
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
req.alt-api: IOCTL_GNSS_LISTEN_DRIVER_REQUEST
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

# IOCTL_GNSS_LISTEN_DRIVER_REQUEST IOCTL



## -description
<p>The <b>IOCTL_GNSS_LISTEN_DRIVER_REQUEST</b> control code is used by the GNSS driver to get data from the HLOS.</p>


## -ioctlparameters

### -input-buffer
<p>Set to NULL.</p>

### -input-buffer-length
<p>Set to 0.</p>

<p>Set to 0.</p>

### -output-buffer
<p>A pointer to a <a href="sensors.gnss_event">GNSS_EVENT</a> structure.</p>

<p>The <b>EventType</b> must be set to <b>GNSS_Event_DriverRequest</b> and the <b>DriverRequestedData</b> member filled in.</p>

<p>A pointer to a <a href="sensors.gnss_event">GNSS_EVENT</a> structure.</p>

<p>The <b>EventType</b> must be set to <b>GNSS_Event_DriverRequest</b> and the <b>DriverRequestedData</b> member filled in.</p>

<p>A pointer to a <a href="sensors.gnss_event">GNSS_EVENT</a> structure.</p>

<p>The <b>EventType</b> must be set to <b>GNSS_Event_DriverRequest</b> and the <b>DriverRequestedData</b> member filled in.</p>

### -output-buffer-length
<p>Set to sizeof(GNSS_EVENT).</p>

<p>Set to sizeof(GNSS_EVENT).</p>

<p>Set to sizeof(GNSS_EVENT).</p>

<p>Set to sizeof(GNSS_EVENT).</p>

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
<p>The GNSS adapter keeps a pending request all the time.</p>

<p>When the driver completes the I/O call, the adapter issues another IOCTL to receive the next driver request.</p>

<p>There will be a pending IOCTL all the time. Whenever there is a need to request data from HLOS the I/O operation should be completed. The GNSS driver should fill out the required data requested by filling the <a href="..\gnssdriver\ns-gnssdriver-gnss-driver-request-data.md">GNSS_DRIVER_REQUEST_DATA</a> structure.</p>

<p>The driver should use this IOCTL to get data in only rare circumstances and not during normal operations. On possible use case would be to request SUPL configuration if somehow the configuration is lost.</p>

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
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_LISTEN_DRIVER_REQUEST control code%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
