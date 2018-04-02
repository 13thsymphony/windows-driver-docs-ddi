---
UID: NI:ntddpar.IOCTL_PAR_QUERY_DEVICE_ID_SIZE
title: IOCTL_PAR_QUERY_DEVICE_ID_SIZE
author: windows-driver-content
description: The IOCTL_PAR_QUERY_DEVICE_ID_SIZE request returns the size, in bytes, of a buffer that can hold a device's IEEE 1284 device ID and a NULL terminator.
old-location: parports\ioctl_par_query_device_id_size.htm
old-project: parports
ms.assetid: f593e36e-8c2b-4cdc-ade1-d1e260f37667
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_PAR_QUERY_DEVICE_ID_SIZE, IOCTL_PAR_QUERY_DEVICE_ID_SIZE control code [Parallel Ports], cisspd_a1c3f5cd-d1bc-40e5-a1e0-dc4306107826.xml, ntddpar/IOCTL_PAR_QUERY_DEVICE_ID_SIZE, parports.ioctl_par_query_device_id_size
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddpar.h
req.include-header: Ntddpar.h
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
-	ntddpar.h
api_name:
-	IOCTL_PAR_QUERY_DEVICE_ID_SIZE
product: Windows
targetos: Windows
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
---

# IOCTL_PAR_QUERY_DEVICE_ID_SIZE IOCTL
The IOCTL_PAR_QUERY_DEVICE_ID_SIZE request returns the size, in bytes, of a buffer that can hold a device's IEEE 1284 device ID and a <b>NULL</b> terminator.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="..\ntddpar\ns-ntddpar-_par_device_id_size_information.md">PAR_DEVICE_ID_SIZE_INFORMATION</a> structure that the client allocates to output the device ID size information. The system-supplied bus driver for parallel ports sets the <b>DeviceIdSize</b> member of the output structure to the size, in bytes, of a buffer that can hold the device ID and a <b>NULL</b> terminator.

### Output Buffer Length
The length of a <a href="..\ntddpar\ns-ntddpar-_par_device_id_size_information.md">PAR_DEVICE_ID_SIZE_INFORMATION</a> structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a PAR_DEVICE_ID_SIZE_INFORMATION structure. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to STATUS_IO_DEVICE_ERROR


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddpar.h (include Ntddpar.h) |

## See Also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id.md">IOCTL_PAR_QUERY_DEVICE_ID</a>



<a href="..\ntddpar\ns-ntddpar-_par_device_id_size_information.md">PAR_DEVICE_ID_SIZE_INFORMATION</a>