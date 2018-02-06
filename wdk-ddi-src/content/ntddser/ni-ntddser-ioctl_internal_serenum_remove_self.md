---
UID: NI:ntddser.IOCTL_INTERNAL_SERENUM_REMOVE_SELF
title: IOCTL_INTERNAL_SERENUM_REMOVE_SELF
author: windows-driver-content
description: The IOCTL_INTERNAL_SERENUM_REMOVE_SELF request invalidates the bus relations of the filter DO that are associated with a target PDO. (Physically, this request invalidates the bus relations of the RS-232 port to which the target device is attached.).
old-location: serports\ioctl_internal_serenum_remove_self.htm
old-project: serports
ms.assetid: 1607439d-fc94-4ebd-84c8-bb5cabdeaab9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: serports.ioctl_internal_serenum_remove_self, IOCTL_INTERNAL_SERENUM_REMOVE_SELF control code [Serial Ports], IOCTL_INTERNAL_SERENUM_REMOVE_SELF, ntddser/IOCTL_INTERNAL_SERENUM_REMOVE_SELF, senumref_e7d31955-3eb4-4769-a7fa-84b55272f47a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
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
-	ntddser.h
apiname:
-	IOCTL_INTERNAL_SERENUM_REMOVE_SELF
product: Windows
targetos: Windows
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_INTERNAL_SERENUM_REMOVE_SELF IOCTL
The IOCTL_INTERNAL_SERENUM_REMOVE_SELF request invalidates the bus relations of the filter DO that are associated with a target PDO. (Physically, this request invalidates the bus relations of the RS-232 port to which the target device is attached.)

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
The <b>Status</b> member is set to one of the following values:


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddser.h (include Ntddser.h) |