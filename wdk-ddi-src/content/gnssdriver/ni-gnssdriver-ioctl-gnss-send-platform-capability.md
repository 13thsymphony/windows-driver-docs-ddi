---
UID: NI.gnssdriver.IOCTL_GNSS_SEND_PLATFORM_CAPABILITY
title: IOCTL_GNSS_SEND_PLATFORM_CAPABILITY
author: windows-driver-content
description: The IOCTL_GNSS_SEND_PLATFORM_CAPABILITY control code is used by the GNSS adapter to communicate the various location-specific platform capabilities.
old-location: sensors\ioctl_gnss_send_platform_capability.htm
old-project: sensors
ms.assetid: EF979267-BDF3-4C42-B18E-C77E2584BC2D
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
req.alt-api: IOCTL_GNSS_SEND_PLATFORM_CAPABILITY
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

# IOCTL_GNSS_SEND_PLATFORM_CAPABILITY IOCTL



## -description
<p>The <b>IOCTL_GNSS_SEND_PLATFORM_CAPABILITY</b> control code is used by the GNSS adapter to communicate the various location-specific platform capabilities. The GNSS driver can use this data in various ways. For example, if the platform does not support injection of assistance data, the GNSS driver can use the mobile operation network to seek such information. The use of the individual capability information is optional and the driver can ignore the platform capability information for its operation.</p>


## -ioctlparameters

### -input-buffer
<p>A pointer to a <a href="sensors.gnss_platform_capability">GNSS_PLATFORM_CAPABILITY</a> structure.

</p>

### -input-buffer-length
<p>Set to sizeof(GNSS_PLATFORM_CAPABILITY).</p>

<p>Set to sizeof(GNSS_PLATFORM_CAPABILITY).</p>

### -output-buffer
<p>Set to NULL.</p>

<p>Set to NULL.</p>

<p>Set to NULL.</p>

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
<p>The driver sets one of the following NTSTATUS values to indicate result.</p>

<p><b>STATUS_SUCCESS</b>, when the driver processes the capability information successfully.</p>

<p><b>Failed</b>, when the driver does not process the capability information successfully.</p>

<p><b>Ignored</b>, when the driver ignores the capability information.</p>

<p>This is a void fire-and-forget style call to the driver. The GNSS adapter does not do any special error handling even when the call fails.</p>

<p>The driver can record the capability information in state variables and pass on to the engine as needed. The I/O should be completed as soon as the configuration information is copied.</p>

<p>This should be called when the GNSS adapter is initializing the GNSS driver.</p>

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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_SEND_PLATFORM_CAPABILITY control code%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
