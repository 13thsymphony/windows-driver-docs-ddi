---
UID: NI:kbdmou.IOCTL_INTERNAL_KEYBOARD_DISCONNECT
title: IOCTL_INTERNAL_KEYBOARD_DISCONNECT
author: windows-driver-content
description: The IOCTL_INTERNAL_KEYBOARD_DISCONNECT request is completed with a status of STATUS_NOT_IMPLEMENTED. Note that a Plug and Play keyboard can be added or removed by the Plug and Play manager.
old-location: hid\ioctl_internal_keyboard_disconnect.htm
old-project: hid
ms.assetid: ec1c2267-b92c-4d4c-86fa-f2b3ccb6aa40
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_INTERNAL_KEYBOARD_DISCONNECT, IOCTL_INTERNAL_KEYBOARD_DISCONNECT control code [Human Input Devices], hid.ioctl_internal_keyboard_disconnect, kbdmou/IOCTL_INTERNAL_KEYBOARD_DISCONNECT, kfilref_fd52cb0d-fbdd-44fb-9c71-ec829387a88b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: kbdmou.h
req.include-header: Kbdmou.h
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
-	kbdmou.h
api_name:
-	IOCTL_INTERNAL_KEYBOARD_DISCONNECT
product: Windows
targetos: Windows
req.typenames: MSiSCSI_SessionStatistics, *PMSiSCSI_SessionStatistics
---

# IOCTL_INTERNAL_KEYBOARD_DISCONNECT IOCTL
The IOCTL_INTERNAL_KEYBOARD_DISCONNECT request is completed with a status of STATUS_NOT_IMPLEMENTED. Note that a Plug and Play keyboard can be added or removed by the Plug and Play manager.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None

### Input Buffer Length
None

### Output Buffer
None

### Output Buffer Length
None

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Status</b> member is set to STATUS_NOT_IMPLEMENTED.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | kbdmou.h (include Kbdmou.h) |

## See Also

<a href="..\kbdmou\ni-kbdmou-ioctl_internal_keyboard_connect.md">IOCTL_INTERNAL_KEYBOARD_CONNECT</a>