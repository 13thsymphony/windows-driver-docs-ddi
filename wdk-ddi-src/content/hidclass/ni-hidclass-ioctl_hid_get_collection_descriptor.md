---
UID: NI:hidclass.IOCTL_HID_GET_COLLECTION_DESCRIPTOR
title: IOCTL_HID_GET_COLLECTION_DESCRIPTOR
author: windows-driver-content
description: The IOCTL_HID_GET_COLLECTION_DESCRIPTOR request obtains a top-level collection's preparsed data, which the HID class driver extracted from the physical device's report descriptor during device initialization.
old-location: hid\ioctl_hid_get_collection_descriptor.htm
old-project: hid
ms.assetid: 93684a1a-788d-4b90-b9cc-58a3c4f7b25e
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.ioctl_hid_get_collection_descriptor, IOCTL_HID_GET_COLLECTION_DESCRIPTOR control code [Human Input Devices], IOCTL_HID_GET_COLLECTION_DESCRIPTOR, hidclass/IOCTL_HID_GET_COLLECTION_DESCRIPTOR, hidioreq_3b297887-5287-463a-9a31-46b8bd7761b3.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hidclass.h
apiname:
-	IOCTL_HID_GET_COLLECTION_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---

# IOCTL_HID_GET_COLLECTION_DESCRIPTOR IOCTL
The IOCTL_HID_GET_COLLECTION_DESCRIPTOR request obtains a top-level collection's <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>, which the HID class driver extracted from the physical device's report descriptor during device initialization.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer specified by <b>Irp-&gt;UserBuffer</b>.

### Input Buffer Length
<text></text>

### Output Buffer
<b>Irp-&gt;UserBuffer</b> is a PVOID pointer to a requester-allocated buffer that the HID class driver uses to return a variable length <b>_HIDP_PREPARSED_DATA</b> structure. This buffer must be allocated from nonpaged pool.

### Output Buffer Length
The size, in bytes, of the preparsed data structure is obtained using <a href="..\hidclass\ni-hidclass-ioctl_hid_get_collection_information.md">IOCTL_HID_GET_COLLECTION_INFORMATION</a>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to size, in bytes, of the preparesed data.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the preparsed data was retrieved without error. Otherwise, it is set to an appropriate NTSTATUS error code. If the requester-supplied output buffer is not large enough to hold the preparsed data, then status is set to STATUS_INVALID_BUFFER_SIZE. 

</li>
</ul>

## Remarks
The <b>_HIDP_PREPARSED_DATA</b> structure contains a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection's</a> <a href="https://msdn.microsoft.com/50ac2877-4c45-4d55-b5cc-013486892fbf">preparsed data</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _HIDP_PREPARSED_DATA * PHIDP_PREPARSED_DATA;
</pre>
</td>
</tr>
</table></span></div>
A user-mode application calls <a href="..\hidsdi\nf-hidsdi-hidd_getpreparseddata.md">HidD_GetPreparsedData</a> to obtain a top-level collection's preparsed data in a variable length _HIDP_PREPARSED_DATA structure.

A kernel-mode driver uses an <b>IOCTL_HID_GET_COLLECTION_DESCRIPTOR</b> request to obtain a pointer to a top-level collection's preparsed data.

The internal structure of a _HIDP_PREPARSED_DATA structure is reserved for internal system use.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidclass.h (include Hidclass.h) |

## See Also

<a href="..\hidsdi\nf-hidsdi-hidd_freepreparseddata.md">HidD_FreePreparsedData</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getpreparseddata.md">HidD_GetPreparsedData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_GET_COLLECTION_DESCRIPTOR control code%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>