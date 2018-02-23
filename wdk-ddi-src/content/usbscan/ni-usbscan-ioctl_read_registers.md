---
UID: NI:usbscan.IOCTL_READ_REGISTERS
title: IOCTL_READ_REGISTERS
author: windows-driver-content
description: Reads from USB device registers, using the control pipe.
old-location: image\ioctl_read_registers.htm
old-project: Image
ms.assetid: b54c9a15-0d48-4aff-98e5-1f0dfc070ed6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: image.ioctl_read_registers, IOCTL_READ_REGISTERS control code [Imaging Devices], IOCTL_READ_REGISTERS, usbscan/IOCTL_READ_REGISTERS, stifnc_68af86d1-7d3b-4d2c-a5af-983f0339d71f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbscan.h
req.include-header: Usbscan.h
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
-	Usbscan.h
apiname:
-	IOCTL_READ_REGISTERS
product: Windows
targetos: Windows
req.typenames: RAW_PIPE_TYPE
req.product: Windows 10 or later.
---

# IOCTL_READ_REGISTERS IOCTL
Reads from USB device registers, using the control pipe.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Pointer to an <a href="..\usbscan\ns-usbscan-_io_block.md">IO_BLOCK</a> structure.

### Input Buffer Length
Size of the input buffer.

### Output Buffer
Pointer to a buffer to receive register contents.

### Output Buffer Length
Size of the output buffer. The value must match the contents of the <b>uLength</b> member of the IO_BLOCK structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
<h3><a id="ddk_ioctl_read_registers_si"></a><a id="DDK_IOCTL_READ_REGISTERS_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_READ_REGISTERS I/O control code, the caller must specify the address of an <a href="..\usbscan\ns-usbscan-_io_block.md">IO_BLOCK</a> structure as the function's <i>lpInBuffer</i> parameter.

Using the IO_BLOCK contents, the kernel-mode driver creates a <a href="..\usb\ns-usb-_urb.md">URB</a> that contains a <a href="..\usb\ns-usb-_urb_control_vendor_or_class_request.md">_URB_CONTROL_VENDOR_OR_CLASS_REQUEST</a> structure.

The following table indicates the values assigned to _URB_CONTROL_VENDOR_OR_CLASS_REQUEST structure members.

<table>
<tr>
<th>Structure Member</th>
<th>Value Assigned</th>
</tr>
<tr>
<td>
<b>TransferFlags</b>

</td>
<td>
1

</td>
</tr>
<tr>
<td>
<b>TransferBufferLength</b>

</td>
<td>
<i>pIoBlock</i>-&gt;<b>uLength</b>

</td>
</tr>
<tr>
<td>
<b>TransferBuffer</b>

</td>
<td>

<a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>'s <i>lpOutBuffer</i> argument.

</td>
</tr>
<tr>
<td>
<b>TransferBufferMDL</b>

</td>
<td>
<b>NULL</b>

</td>
</tr>
<tr>
<td>
<b>RequestTypeReservedBits</b>

</td>
<td>
0xC0

</td>
</tr>
<tr>
<td>
<b>Request</b>

</td>
<td>
(<i>pIoBlock</i>-&gt;<b>uLength</b> &gt; 1) ? 0x04 : 0x0C

</td>
</tr>
<tr>
<td>
<b>Value</b>

</td>
<td>
(<b>SHORT</b>)<i>pIoBlock</i>-&gt;<b>uOffset</b>

</td>
</tr>
<tr>
<td>
<b>Index</b>

</td>
<td>
<i>pIoBlock</i>-&gt;<b>uIndex</b>

</td>
</tr>
</table>
 

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbscan.h (include Usbscan.h) |