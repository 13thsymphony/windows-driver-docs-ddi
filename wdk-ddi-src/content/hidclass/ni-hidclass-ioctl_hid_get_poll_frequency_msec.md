---
UID: NI:hidclass.IOCTL_HID_GET_POLL_FREQUENCY_MSEC
title: IOCTL_HID_GET_POLL_FREQUENCY_MSEC
author: windows-driver-content
description: The IOCTL_HID_GET_POLL_FREQUENCY_MSEC request obtains the current polling frequency, in milliseconds, of a top-level collection.
old-location: hid\ioctl_hid_get_poll_frequency_msec.htm
old-project: hid
ms.assetid: 602dc6ac-89cc-4feb-9cef-5226c8abb085
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_GET_POLL_FREQUENCY_MSEC, IOCTL_HID_GET_POLL_FREQUENCY_MSEC control code [Human Input Devices], hid.ioctl_hid_get_poll_frequency_msec, hidclass/IOCTL_HID_GET_POLL_FREQUENCY_MSEC, hidioreq_e0cd09b6-f27f-4a30-918d-c67c2b52da9d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidclass.h
req.include-header: Hidclass.h
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
-	hidclass.h
api_name:
-	IOCTL_HID_GET_POLL_FREQUENCY_MSEC
product: Windows
targetos: Windows
req.typenames: HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---

# IOCTL_HID_GET_POLL_FREQUENCY_MSEC IOCTL
The IOCTL_HID_GET_POLL_FREQUENCY_MSEC request obtains the current polling frequency, in milliseconds, of a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be &gt;= <b>sizeof</b>(ULONG).

### Input Buffer Length
Greater than or equal to <b>sizeof</b>(ULONG).

### Output Buffer
<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a buffer that will receive the polling frequency.

### Output Buffer Length


### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to <b>sizeof</b>(ULONG) if the polling frequency is successfully retrieved. 

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

<a href="..\hidclass\ni-hidclass-ioctl_hid_set_poll_frequency_msec.md">IOCTL_HID_SET_POLL_FREQUENCY_MSEC</a>