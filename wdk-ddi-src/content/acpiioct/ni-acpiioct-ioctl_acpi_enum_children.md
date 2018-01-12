---
UID: NI:acpiioct.IOCTL_ACPI_ENUM_CHILDREN
title: IOCTL_ACPI_ENUM_CHILDREN
author: windows-driver-content
description: The IOCTL_ACPI_ENUM_CHILDREN device control request can be used to enumerate the path and name of devices or named child objects in the ACPI namespace of the device to which this request is sent.
old-location: acpi\ioctl_acpi_enum_children.htm
old-project: acpi
ms.assetid: 86d713e0-ec1e-4417-9ff7-8574bd040a6e
ms.author: windowsdriverdev
ms.date: 12/31/2017
ms.keywords: _UNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_ACPI_ENUM_CHILDREN
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
req.typenames: UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
---

# IOCTL_ACPI_ENUM_CHILDREN IOCTL



## -description
The IOCTL_ACPI_ENUM_CHILDREN device control request can be used to enumerate the path and name of devices or named child objects in the ACPI namespace of the device to which this request is sent. A driver should call <a href="..\wdm\nf-wdm-iobuilddeviceiocontrolrequest.md">IoBuildDeviceIoControlRequest</a> and pass the following input and output parameters to build this request. 



## -ioctlparameters

### -input-buffer
Set the <b>IoBuildDeviceIoControlRequest</b> input parameters as follows:

<i>IoControlCode</i> is set to IOCTL_ACPI_ENUM_CHILDREN.

<i>DeviceObject</i> is set to a pointer to the physical device object (PDO) of the device.

<i>InputBuffer</i> is set to a pointer to a variable-length <a href="..\acpiioct\ns-acpiioct-_acpi_enum_children_input_buffer.md">ACPI_ENUM_CHILDREN_INPUT_BUFFER</a> structure.

<i>InputBufferLength</i> is set to the size, in bytes, of the input buffer that is supplied by <i>InputBuffer</i>.

<i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.

<i>InternalDeviceIoControl</i> is set to <b>FALSE</b>.

<i>Event</i> is set to a pointer to a caller-allocated and initialized event object.


### -input-buffer-length
<i>InputBufferLength</i> is set to the size, in bytes, of the input buffer that is supplied by <i>InputBuffer</i>.


### -output-buffer
Set the <b>IoBuildDeviceIoControlRequest</b> output parameters as follows:

<i>OutputBuffer</i> supplies a pointer to a variable-length <a href="..\acpiioct\ns-acpiioct-_acpi_enum_children_output_buffer.md">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a> structure in which the ACPI driver returns the path and name of the enumerated child devices.

<i>IoStatusBlock</i> is set to an <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure.


### -output-buffer-length
<i>OutputBufferLength</i> supplies the size, in bytes, of the output buffer that is supplied by <i>OutputBuffer</i>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request succeeds, <i>IoStatusBlock</i>-&gt;<b>Status</b> is set to STATUS_SUCCESS; otherwise, the <b>Status</b> member is set to an error code. If the output buffer is not large enough to contain the buffer header, the <b>Status</b> member is set to STATUS_BUFFER_TOO_SMALL. If the output buffer is large enough to contain the output buffer header, but is not large enough to contain the paths and names of all the enumerated child objects, the <b>Status</b> member is set to STATUS_BUFFER_OVERFLOW and <i>OutputBuffer</i>-&gt;<b>NumberOfChildren</b> is set to the required length of the output buffer.

If the request succeeds, the <i>IoStatusBlock</i>-&gt;<b>Information</b> member is set to the number of bytes that is returned in the output buffer; otherwise, the <b>Information</b> member is set to zero.


## -remarks
IOCTL_ACPI_ENUM_CHILDREN returns a variable-length ACPI_ENUM_CHILDREN_OUTPUT_BUFFER structure that contains an array of variable-length <a href="..\acpiioct\ns-acpiioct-_acpi_enum_child.md">ACPI_ENUM_CHILD</a> structures, each of which returns the fully qualified path and name of an object in the ACPI namespace of the device to which the request was sent. The objects that this request enumerates depends on the setting of the <b>Flags</b> member of the supplied input structure ACPI_ENUM_CHILDREN_INPUT_BUFFER, as follows:



Enumerates the device and enumerates the immediate child devices of the device.

Enumerates the device and recursively enumerates all child devices of the device.

A bitwise OR of ENUM_CHILDREN and ENUM_CHILDREN_NAME_IS_FILTER enumerates the device's child objects whose name is identical to that supplied by the <b>Name</b> member.

If the output buffer that the driver allocates is not large enough to return all requested child names, the ACPI driver does not return any child names and sets the <b>Status</b> member of the IO_STATUS_BLOCK for the request to STATUS_BUFFER_OVERFLOW. In this case, if the size, in bytes, of the output buffer is at least <b>sizeof</b>(ACPI_ENUM_CHILDREN_OUTPUT_BUFFER_SIGNATURE), the ACPI driver also sets <i>NumberOfChildren</i> to the size, in bytes, that is required to retrieve the requested paths and names. 

A driver typically would use a sequence of two IOCTL_ACPI_ENUM_CHILDREN requests to enumerate the child objects of interest. The driver sends the first request to obtain the size of the output buffer that is required to contain the path and name of all the requested objects. The driver sends the second request to return the path and name of the objects in the output buffer. 

For more information about how to enumerate child devices of a device, see <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/acpi/enumerating-child-devices-and-control-methods">Enumerating Child Devices and Control Methods</a>.

IOCTL_ACPI_ENUM_CHILDREN can be used only at IRQL&lt; DISPATCH_LEVEL.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows Vista and later versions of Windows.

</td>
</tr>
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
<a href="..\acpiioct\ns-acpiioct-_acpi_enum_child.md">ACPI_ENUM_CHILD</a>
</dt>
<dt>
<a href="..\acpiioct\ns-acpiioct-_acpi_enum_children_input_buffer.md">ACPI_ENUM_CHILDREN_INPUT_BUFFER</a>
</dt>
<dt>
<a href="..\acpiioct\ns-acpiioct-_acpi_enum_children_output_buffer.md">ACPI_ENUM_CHILDREN_OUTPUT_BUFFER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [acpi\acpi]:%20IOCTL_ACPI_ENUM_CHILDREN control code%20 RELEASE:%20(12/31/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

