---
UID: NI.gnssdriver.IOCTL_GNSS_EXECUTE_CWTEST
title: IOCTL_GNSS_EXECUTE_CWTEST
author: windows-driver-content
description: The IOCTL_GNSS_EXECUTE_CWTEST control code is used by the GNSS manufacturing test application to start a carrier wave test and get the measurement. The test application must wait for the result before starting another iteration of the measurement.
old-location: sensors\ioctl_gnss_execute_cwtest.htm
old-project: sensors
ms.assetid: 36AFBB03-9F01-4CA7-A5E8-C6F744984B6F
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
req.alt-api: IOCTL_GNSS_EXECUTE_CWTEST
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

# IOCTL_GNSS_EXECUTE_CWTEST IOCTL



## -description
<p>The <b>IOCTL_GNSS_EXECUTE_CWTEST</b> control code is used by the GNSS manufacturing test application to start a carrier wave test and get the measurement. The test application must wait for the result before starting another iteration of the measurement.</p>


## -ioctlparameters

### -input-buffer
<p>Set to NULL.</p>

### -input-buffer-length
<p>Set to 0.</p>

<p>Set to 0.</p>

### -output-buffer
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925102">GNSS_CWTESTDATA</a> structure.</p>

<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925102">GNSS_CWTESTDATA</a> structure.</p>

<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925102">GNSS_CWTESTDATA</a> structure.</p>

### -output-buffer-length
<p>Set to sizeof(GNSS_CWTESTDATA).</p>

<p>Set to sizeof(GNSS_CWTESTDATA).</p>

<p>Set to sizeof(GNSS_CWTESTDATA).</p>

<p>Set to sizeof(GNSS_CWTESTDATA).</p>

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
<p>The test application must ensure that no more than one carrier wave test is started at the same time.</p>

<p>Once the carrier wave test is started, the test application must wait for the result.</p>

<p>The test application will need to repeat this command if it wants to retrieve more than one measurement.</p>

<p>The GNSS driver must fail the new carrier wave test session request if there is already a test in progress.</p>

<p>Once the GNSS driver accepts the carrier wave test session parameters, validates them and starts the detection in the GNSS engine. When the measurements are received, the driver immediately completes the IO with a return code and the measurements.</p>

<p>The GNSS stack must return the measurements as soon as they are available.</p>

<p>The test application must ensure that no more than one carrier wave test is started at the same time.</p>

<p>Once the carrier wave test is started, the test application must wait for the result.</p>

<p>The test application will need to repeat this command if it wants to retrieve more than one measurement.</p>

<p>The GNSS driver must fail the new carrier wave test session request if there is already a test in progress.</p>

<p>Once the GNSS driver accepts the carrier wave test session parameters, validates them and starts the detection in the GNSS engine. When the measurements are received, the driver immediately completes the IO with a return code and the measurements.</p>

<p>The GNSS stack must return the measurements as soon as they are available.</p>

<p>The test application must ensure that no more than one carrier wave test is started at the same time.</p>

<p>Once the carrier wave test is started, the test application must wait for the result.</p>

<p>The test application will need to repeat this command if it wants to retrieve more than one measurement.</p>

<p>The GNSS driver must fail the new carrier wave test session request if there is already a test in progress.</p>

<p>Once the GNSS driver accepts the carrier wave test session parameters, validates them and starts the detection in the GNSS engine. When the measurements are received, the driver immediately completes the IO with a return code and the measurements.</p>

<p>The GNSS stack must return the measurements as soon as they are available.</p>

<p>The test application must ensure that no more than one carrier wave test is started at the same time.</p>

<p>Once the carrier wave test is started, the test application must wait for the result.</p>

<p>The test application will need to repeat this command if it wants to retrieve more than one measurement.</p>

<p>The GNSS driver must fail the new carrier wave test session request if there is already a test in progress.</p>

<p>Once the GNSS driver accepts the carrier wave test session parameters, validates them and starts the detection in the GNSS engine. When the measurements are received, the driver immediately completes the IO with a return code and the measurements.</p>

<p>The GNSS stack must return the measurements as soon as they are available.</p>

<p>The test application must ensure that no more than one carrier wave test is started at the same time.</p>

<p>Once the carrier wave test is started, the test application must wait for the result.</p>

<p>The test application will need to repeat this command if it wants to retrieve more than one measurement.</p>

<p>The GNSS driver must fail the new carrier wave test session request if there is already a test in progress.</p>

<p>Once the GNSS driver accepts the carrier wave test session parameters, validates them and starts the detection in the GNSS engine. When the measurements are received, the driver immediately completes the IO with a return code and the measurements.</p>

<p>The GNSS stack must return the measurements as soon as they are available.</p>

<p>The test application must ensure that no more than one carrier wave test is started at the same time.</p>

<p>Once the carrier wave test is started, the test application must wait for the result.</p>

<p>The test application will need to repeat this command if it wants to retrieve more than one measurement.</p>

<p>The GNSS driver must fail the new carrier wave test session request if there is already a test in progress.</p>

<p>Once the GNSS driver accepts the carrier wave test session parameters, validates them and starts the detection in the GNSS engine. When the measurements are received, the driver immediately completes the IO with a return code and the measurements.</p>

<p>The GNSS stack must return the measurements as soon as they are available.</p>

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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_EXECUTE_CWTEST control code%20 RELEASE:%20(11/26/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
