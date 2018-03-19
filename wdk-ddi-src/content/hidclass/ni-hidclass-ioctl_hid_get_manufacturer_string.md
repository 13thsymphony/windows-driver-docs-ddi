---
UID: NI:hidclass.IOCTL_HID_GET_MANUFACTURER_STRING
title: IOCTL_HID_GET_MANUFACTURER_STRING
author: windows-driver-content
description: The IOCTL_HID_GET_MANUFACTURER_STRING request obtains a top-level collection's embedded string that identifies the manufacturer of the device.
old-location: hid\ioctl_hid_get_manufacturer_string.htm
old-project: hid
ms.assetid: 1a402deb-132c-4cda-a019-e044318e1910
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_GET_MANUFACTURER_STRING, IOCTL_HID_GET_MANUFACTURER_STRING control code [Human Input Devices], hid.ioctl_hid_get_manufacturer_string, hidclass/IOCTL_HID_GET_MANUFACTURER_STRING, hidioreq_05724f70-c708-4f9a-ba51-fa2edabf56ed.xml
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
-	IOCTL_HID_GET_MANUFACTURER_STRING
product: Windows
targetos: Windows
req.typenames: HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---

# IOCTL_HID_GET_MANUFACTURER_STRING IOCTL
The IOCTL_HID_GET_MANUFACTURER_STRING request obtains a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> embedded string that identifies the manufacturer of the device. The retrieved string is a NULL-terminated wide character string in a human-readable format.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer. If the output buffer is not large enough to hold the entire NULL-terminated embedded string, the request returns nothing in the output buffer.

### Input Buffer Length
The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

### Output Buffer
<b>Irp-&gt;MdlAddress</b> points to a buffer to receive the manufacturer ID (a NULL-terminated wide character string).

### Output Buffer Length
<text></text>

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred from the device.

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

<a href="..\hidsdi\nf-hidsdi-hidd_getmanufacturerstring.md">HidD_GetManufacturerString</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getindexedstring.md">HidD_GetIndexedString</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getserialnumberstring.md">HidD_GetSerialNumberString</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getphysicaldescriptor.md">HidD_GetPhysicalDescriptor</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_indexed_string.md">IOCTL_HID_GET_INDEXED_STRING</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_product_string.md">IOCTL_HID_GET_PRODUCT_STRING</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getproductstring.md">HidD_GetProductString</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_serialnumber_string.md">IOCTL_HID_GET_SERIALNUMBER_STRING</a>