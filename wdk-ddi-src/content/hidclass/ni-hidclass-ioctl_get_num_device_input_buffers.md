---
UID : NI:hidclass.IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS
title : IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS
author : windows-driver-content
description : The IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS request obtains the size of the input report queue for a top-level collection.
old-location : hid\ioctl_get_num_device_input_buffers.htm
old-project : hid
ms.assetid : 3a0a8fa3-2d23-412c-ad54-d8ba5809cbe4
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : hid.ioctl_get_num_device_input_buffers, IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS control code [Human Input Devices], IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS, hidclass/IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS, hidioreq_4d76e323-5cc1-40d2-aa56-ca5427f15e6f.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : hidclass.h
req.include-header : Hidclass.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---

# IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS IOCTL
The IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS request obtains the size of the input report queue for a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>. 

The input report queue is implemented as a ring buffer. If a collection transmits data to the HID class driver faster than the input reports are read, reports can be lost. The size of the input report queue can be adjusted using <a href="..\hidclass\ni-hidclass-ioctl_set_num_device_input_buffers.md">IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS</a>. 

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be &gt;= <b>sizeof</b>(ULONG).

### Input Buffer Length
The size of the buffer is <b>sizeof</b>(ULONG).

### Output Buffer
<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a buffer that will receive the size of the report input queue.

### Output Buffer Length
The size of the buffer is <b>sizeof</b>(ULONG).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:
<ul>
<li>
<b>Information</b> is set to <b>sizeof</b>(ULONG) if the size of the report input queue is successfully retrieved. 

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidclass.h (include Hidclass.h) |

## See Also

<a href="..\hidsdi\nf-hidsdi-hidd_setnuminputbuffers.md">HidD_SetNumInputBuffers</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>