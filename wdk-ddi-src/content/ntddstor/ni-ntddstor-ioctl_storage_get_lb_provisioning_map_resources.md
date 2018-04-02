---
UID: NI:ntddstor.IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES
title: IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES
author: windows-driver-content
description: The IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES request is sent to the storage class driver to determine available and used mapping resources on a storage device.
old-location: storage\ioctl_storage_get_lb_provisioning_map_resources.htm
old-project: storage
ms.assetid: 117F6507-CA52-4EA7-9633-75ADB19F4DDA
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES, IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES control code [Storage Devices], ntddstor/IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES, storage.ioctl_storage_get_lb_provisioning_map_resources
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8 and later versions of Windows.
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
-	Ntddstor.h
api_name:
-	IOCTL_STORAGE_GET_LB_PROVISIONING_MAP_RESOURCES
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
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
The buffer at <i>Irp-&gt;AssociatedIrp.SystemBuffer</i> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/hh451465">STORAGE_LB_PROVISIONING_MAP_RESOURCES</a> structure.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451465">STORAGE_LB_PROVISIONING_MAP_RESOURCES</a>