---
UID: NI:ehstorioctl.IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS
title: IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS
author: windows-driver-content
description: This IOCTL returns a result set containing the enumeration of all active storage Physical Device Objects (PDOs) associated with the given Addressable Command Target (ACT).
old-location: storage\ioctl_ehstor_device_enumerate_pdos.htm
old-project: storage
ms.assetid: 900A8CAB-287D-4D92-B4CB-2959E87C8E67
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS, IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS control code [Storage Devices], ehstorioctl/IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS, storage.ioctl_ehstor_device_enumerate_pdos
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
-	EhStorIoctl.h
api_name:
-	IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS
product: Windows
targetos: Windows
req.typenames: PDO_TYPE
---

# IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS IOCTL
This IOCTL returns a result set containing the enumeration of all active storage Physical Device Objects (PDOs) associated with the given Addressable Command Target (ACT). The client may first probe for the required buffer size by issuing this IOCTL in the following manner:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DeviceIoControl(
    hDevice,
    IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS,
    &amp;pdoType,
    sizeof(PDO_TYPE),
    NULL,
    0,
    &amp;dwBytesRequired,
    NULL );</pre>
</td>
</tr>
</table></span></div>
With the output buffer parameter set to <b>NULL</b>, the I/O manager clears the IRP_INPUT_OPERATION bit in the IRP flags. Upon detecting this, the storage silo driver can safely set IoStatus.Information to the required buffer size, thus indicating it to the client.

This only works because STATUS_BUFFER_OVERFLOW (0x80000005) is an NT_WARNING() value for which I/O manager copies IoStatus.Information into the lpBytesReturned parameter, returning that value to the client.

Caution is required here because IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS is defined with METHOD_BUFFERED, therefore I/O manager will attempt to copy this number of bytes into the output buffer.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The input buffer at Irp-&gt;AssociatedIrp.SystemBuffer must contain a ULONG value as defined in <a href="..\ehstorioctl\ne-ehstorioctl-_pdo_type.md">PDO_TYPE</a>,

where either all of the PDOs, just the disk PDO, just the control PDO or all silo PDOs are enumerated respectively according to the provided PDO_TYPE input value.

### Input Buffer Length
The length of a ULONG.

### Output Buffer
Irp-&gt;AssociatedIrp.SystemBuffer points to the buffer that will receive the PDO enumeration results. If the client supplied a non-<b>NULL</b> buffer with the issued IOCTL, then the driver fills it with the result set only if the Parameters.DeviceIoControl.The return value is STATUS_SUCCESS if the buffer size is sufficient and the results have been copied to the buffer. Otherwise STATUS_INVALID_BUFFER_SIZE is returned and the output buffer is unmodified.

The returned enumeration buffer contains a result set structured according to the following rules. The leading structure in the buffer, <a href="..\ehstorioctl\ns-ehstorioctl-_enum_pdo_results.md">ENUM_PDO_RESULTS</a>, consists of a structure count and an array of <a href="..\ehstorioctl\ns-ehstorioctl-_enum_pdo_entry.md">ENUM_PDO_ENTRY</a> structures.

### Output Buffer Length
OutputBufferLength indicates a buffer size of sufficient length to include the entire result set.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
One of the following values may be returned in the Status field:


<dl>
<dd>
STATUS_SUCCESS - The output buffer contains the enumeration of the requested PDOs.

</dd>
</dl>



<dl>
<dd>
STATUS_BUFFER_OVERFLOW - The Information field is set to the required buffer size to contain the entire enumeration result set output.

</dd>
</dl>



<dl>
<dd>
STATUS_INVALID_BUFFER_SIZE - The output buffer length supplied is insufficient to contain the entire enumeration result set output.

</dd>
</dl>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ehstorioctl.h (include EhStorIoctl.h) |