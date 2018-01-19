---
UID : NI:ntddchgr.IOCTL_CHANGER_QUERY_VOLUME_TAGS
title : IOCTL_CHANGER_QUERY_VOLUME_TAGS
author : windows-driver-content
description : Returns volume tag information for the specified elements.
old-location : storage\ioctl_changer_query_volume_tags.htm
old-project : storage
ms.assetid : d2edc681-2a12-4281-81f5-147cf6c5e68f
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _ELEMENT_TYPE, *PELEMENT_TYPE, ELEMENT_TYPE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddchgr.h
req.include-header : Ntddchgr.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_CHANGER_QUERY_VOLUME_TAGS
req.alt-loc : Ntddchgr.h
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
req.typenames : "*PELEMENT_TYPE, ELEMENT_TYPE"
---

# IOCTL_CHANGER_QUERY_VOLUME_TAGS IOCTL
Returns volume tag information for the specified elements.



Returns volume tag information for the specified elements.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> indicates the starting element for which to return information, the action to perform, and a template to use when searching for volume IDs.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(<a href="..\ntddchgr\ns-ntddchgr-_changer_send_volume_tag_information.md">CHANGER_SEND_VOLUME_TAG_INFORMATION</a>).

### Output Buffer
The driver returns the <a href="..\ntddchgr\ns-ntddchgr-_read_element_address_info.md">READ_ELEMENT_ADDRESS_INFO</a> data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>.

### Output Buffer Length
<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the parameter buffer for output, which must be &gt;= <b>sizeof</b>(READ_ELEMENT_ADDRESS_INFO).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
The <b>Information</b> field is set to the correct output buffer size, in bytes. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, or STATUS_INVALID_ELEMENT_ADDRESS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | ntddchgr.h (include Ntddchgr.h) |
| **IRQL** |  |

    ## See Also

        <dl>
<dt>
<a href="..\ntddchgr\ns-ntddchgr-_read_element_address_info.md">READ_ELEMENT_ADDRESS_INFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CHANGER_QUERY_VOLUME_TAGS control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>