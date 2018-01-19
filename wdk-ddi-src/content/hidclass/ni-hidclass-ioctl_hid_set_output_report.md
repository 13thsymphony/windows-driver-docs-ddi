---
UID : NI:hidclass.IOCTL_HID_SET_OUTPUT_REPORT
title : IOCTL_HID_SET_OUTPUT_REPORT
author : windows-driver-content
description : The IOCTL_HID_SET_OUTPUT_REPORT request sends an output report to a top-level collection.
old-location : hid\ioctl_hid_set_output_report.htm
old-project : hid
ms.assetid : f5c0f3a7-5d90-4a95-9ba0-01aea98d8c79
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT
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
req.alt-api : IOCTL_HID_SET_OUTPUT_REPORT
req.alt-loc : hidclass.h
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
req.typenames : "*PHDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT"
---

# IOCTL_HID_SET_OUTPUT_REPORT IOCTL
The IOCTL_HID_SET_OUTPUT_REPORT request sends an output report to a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to the size, in bytes, of a requester-allocated input buffer that contains a HID class output report.

The input buffer size, in bytes, must be large enough to hold the output report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.

The <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> member points to the input buffer that contains an output report. If the collection includes report IDs, the requester must set the first byte of the buffer to a nonzero report ID. Otherwise, the requester must set the first byte to zero. The output report -- excluding its report ID, if report IDs are used -- is located at ((PUCHAR)<i>ReportBuffer</i> + 1).

### Input Buffer Length
The input buffer size, in bytes, must be large enough to hold the output report -- excluding its report ID, if report IDs are used -- plus one additional byte that specifies a nonzero report ID or zero.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<b>Information</b> is set to zero. 

<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | hidclass.h (include Hidclass.h) |
| **IRQL** |  |

    ## See Also

        <dl>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd_getfeature.md">HidD_GetFeature</a>
</dt>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd_getinputreport.md">HidD_GetInputReport</a>
</dt>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd_setfeature.md">HidD_SetFeature</a>
</dt>
<dt>
<a href="..\hidsdi\nf-hidsdi-hidd_setoutputreport.md">HidD_SetOutputReport</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_feature.md">IOCTL_HID_GET_FEATURE</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_get_input_report.md">IOCTL_HID_GET_INPUT_REPORT</a>
</dt>
<dt>
<a href="..\hidclass\ni-hidclass-ioctl_hid_set_feature.md">IOCTL_HID_SET_FEATURE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_SET_OUTPUT_REPORT control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>