---
UID: NI.acpiioct.IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA
title: IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA
author: windows-driver-content
description: The IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control code is used to get device specific data.
old-location: acpi\ioctl_acpi_get_device_specific_data.htm
old-project: acpi
ms.assetid: D77E272D-833E-40EA-97AA-137E0A219730
ms.author: windowsdriverdev
ms.date: 12/2/2017
ms.keywords: _UNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA
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

# IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA IOCTL



## -description
The <b>IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA</b> control code is used to get device specific data.




## -ioctlparameters

### -input-buffer
An input buffer structure that depends on the type of input arguments to be passed to the control method.

### -input-buffer-length
The size, in bytes, of the input buffer.

### -output-buffer
An output buffer structure that contains the output arguments from the control method.

### -output-buffer-length
The size, in bytes, of the output buffer.

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
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
<a href="wdf.wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>
</dt>
<dt>
<a href="wdf.wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>
</dt>
<dt>
<a href="wdf.wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control code%20 RELEASE:%20(12/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
