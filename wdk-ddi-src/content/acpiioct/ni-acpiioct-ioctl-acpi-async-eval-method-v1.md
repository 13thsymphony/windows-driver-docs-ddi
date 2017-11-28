---
UID: NI.acpiioct.IOCTL_ACPI_ASYNC_EVAL_METHOD_V1
title: IOCTL_ACPI_ASYNC_EVAL_METHOD_V1
author: windows-driver-content
description: The IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 control code asynchronously evaluates an ACPI control method that is supported by the device.
old-location: acpi\ioctl_acpi_async_eval_method_v1.htm
old-project: acpi
ms.assetid: E55FDBCE-604E-4AD1-B51E-140A3E7DB038
ms.author: windowsdriverdev
ms.date: 11/16/2017
ms.keywords: UNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709 and later versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_ACPI_ASYNC_EVAL_METHOD_V1
req.alt-loc: Acpiioct.h
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
---

# IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 IOCTL



## -description
<p>The <b>IOCTL_ACPI_ASYNC_EVAL_METHOD_V1</b> control code asynchronously evaluates an ACPI control method that is supported by the device.</p>


## -ioctlparameters

### -input-buffer
<p>An input buffer structure that depends on the type of input arguments to be passed to the control method.</p>

<p>An input buffer structure that depends on the type of input arguments to be passed to the control method.</p>

### -input-buffer-length
<p>The size, in bytes, of the input buffer.</p>

<p>The size, in bytes, of the input buffer.</p>

<p>The size, in bytes, of the input buffer.</p>

### -output-buffer
<p>An output buffer structure that contains the output arguments from the control method.</p>

<p>An output buffer structure that contains the output arguments from the control method.</p>

<p>An output buffer structure that contains the output arguments from the control method.</p>

<p>An output buffer structure that contains the output arguments from the control method.</p>

### -output-buffer-length
<p>The size, in bytes, of the output buffer.</p>

<p>The size, in bytes, of the output buffer.</p>

<p>The size, in bytes, of the output buffer.</p>

<p>The size, in bytes, of the output buffer.</p>

<p>The size, in bytes, of the output buffer.</p>

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


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Windows 10, version 1709 and later versions.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Acpiioct.h (include Acpiioct.h)</dt>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20IOCTL_ACPI_ASYNC_EVAL_METHOD_V1 control code%20 RELEASE:%20(11/16/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
