---
UID : NI:ntddstor.IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES
title : IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES
author : windows-driver-content
description : The IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES request is sent to the storage class driver to determine available and used mapping resources on a storage device.
old-location : storage\ioctl_storage_get_lb_provisioning_map_resources.htm
old-project : storage
ms.assetid : 117F6507-CA52-4EA7-9633-75ADB19F4DDA
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ioctl_storage_get_lb_provisioning_map_resources, IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES control code [Storage Devices], IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES, ntddstor/IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : ntddstor.h
req.include-header : Ntddstor.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 8 and later versions of Windows.
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
req.typenames : STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES IOCTL
The <b>IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES</b> request is sent to the storage class driver to determine available and used mapping resources on a storage device.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> contains a <a href="..\ntddstor\ns-ntddstor-_storage_lb_provisioning_map_resources.md">STORAGE_LB_PROVISIONING_MAP_RESOURCES</a> structure.

### Output Buffer Length
<i>Parameters.DeviceIoControl.OutputBufferLength</i> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer, which must be at least <b>sizeof</b>(STORAGE_LB_PROVISIONING_MAP_RESOURCES).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Status</b> field can be set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_BUFFER_TOO_SMALL, STATUS_BUFFER_OVERFLOW, or some other error status.

## Remarks
If logical block provisioning is enabled on a LUN, resource mapping counts  may be reported from the storage device. Resource mapping information is obtained by using the <b>IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES</b>  request. A storage monitoring application can use this IOCTL to query resource mapping conditions before a resource threshold or exhaustion event is logged.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 8 and later versions of Windows. Available in Windows 8 and later versions of Windows. |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="..\ntddstor\ns-ntddstor-_storage_lb_provisioning_map_resources.md">STORAGE_LB_PROVISIONING_MAP_RESOURCES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>