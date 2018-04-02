---
UID: NI:ntddchgr.IOCTL_CHANGER_GET_STATUS
title: IOCTL_CHANGER_GET_STATUS
author: windows-driver-content
description: Returns the current status of the device.
old-location: storage\ioctl_changer_get_status.htm
old-project: storage
ms.assetid: 88f1a248-0beb-4c7c-b68d-6ce145bf5ca7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_CHANGER_GET_STATUS, IOCTL_CHANGER_GET_STATUS control code [Storage Devices], k307_81e37b47-2d26-466d-9ddc-cc681398d607.xml, ntddchgr/IOCTL_CHANGER_GET_STATUS, storage.ioctl_changer_get_status
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
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
-	Ntddchgr.h
api_name:
-	IOCTL_CHANGER_GET_STATUS
product: Windows
targetos: Windows
req.typenames: ELEMENT_TYPE, *PELEMENT_TYPE
---

# IOCTL_CHANGER_GET_STATUS IOCTL
Returns the current status of the device.

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
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddchgr.h (include Ntddchgr.h) |