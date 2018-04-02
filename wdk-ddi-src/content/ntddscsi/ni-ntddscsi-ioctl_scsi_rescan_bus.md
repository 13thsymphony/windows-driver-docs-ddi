---
UID: NI:ntddscsi.IOCTL_SCSI_RESCAN_BUS
title: IOCTL_SCSI_RESCAN_BUS
author: windows-driver-content
description: Rescans the LUNs on the bus(es).
old-location: storage\ioctl_scsi_rescan_bus.htm
old-project: storage
ms.assetid: d2b1ec10-3d59-469f-a92e-e28a6c2aef92
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_SCSI_RESCAN_BUS, IOCTL_SCSI_RESCAN_BUS control code [Storage Devices], k307_36067418-9daa-4fed-a8a6-98fe65ca7fe2.xml, ntddscsi/IOCTL_SCSI_RESCAN_BUS, storage.ioctl_scsi_rescan_bus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
-	Ntddscsi.h
api_name:
-	IOCTL_SCSI_RESCAN_BUS
product: Windows
targetos: Windows
req.typenames: MP_STORAGE_DIAGNOSTIC_TARGET_TYPE, *PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE
---

# IOCTL_SCSI_RESCAN_BUS IOCTL
Rescans the LUNs on the bus(es). It collects SCSI inquiry data about all devices on the bus(es), while preserving any claims on their respective devices for SCSI class drivers. 

This request is obsolete and is supported for legacy code only. This request must be directed to an FDO and is valid only for legacy (non-PnP) class drivers and SCSI bus enumeration. If the bus can detect device insertion, this request is not relevant.

Usually, this request originates in a system-supplied Win32 application such as Windisk or Setup when the user connects new device(s) for which the system has no Plug and Play drivers on a SCSI bus dynamically, that is, without shutting down the system. When this request is satisfied, such an application next makes an <a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a> request to the system port driver and examines the returned inquiry data. If the application finds any unclaimed devices of a given type, it then sends one or more <a href="https://msdn.microsoft.com/library/windows/hardware/ff560546">IOCTL_STORAGE_FIND_NEW_DEVICES</a> requests to the appropriate storage class drivers.


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> field is set to zero. The <b>Status</b> field indicates the results of the operation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560590">IOCTL_STORAGE_QUERY_PROPERTY</a>