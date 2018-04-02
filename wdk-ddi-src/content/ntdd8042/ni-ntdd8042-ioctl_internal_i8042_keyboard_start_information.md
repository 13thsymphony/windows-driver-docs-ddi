---
UID: NI:ntdd8042.IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
title: IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
author: windows-driver-content
description: The IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION request passes a pointer to a keyboard interrupt object.
old-location: hid\ioctl_internal_i8042_keyboard_start_information.htm
old-project: hid
ms.assetid: a589b1e1-7462-4de7-83df-c3d55fa01b76
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION, IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION control code [Human Input Devices], hid.ioctl_internal_i8042_keyboard_start_information, i8042ref_d5599642-48b8-4b77-b4bb-6e0d7596045d.xml, ntdd8042/IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdd8042.h
req.include-header: Ntdd8042.h
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
-	ntdd8042.h
api_name:
-	IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: MOUSE_STATE, *PMOUSE_STATE
---

# IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION IOCTL
The IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION request passes a pointer to a keyboard interrupt object. I8042prt sends this request synchronously to the top of the device stack after the keyboard interrupt object is created. Upper-level filter drivers that need to synchronize their callback operation with the I8042prt keyboard ISR can use the pointer to the keyboard interrupt object.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>AssociatedIrp.SystemBuffer</b> points to a buffer allocated by I8042prt to input an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541052">INTERNAL_I8042_START_INFORMATION</a> structure.

### Input Buffer Length
<b>Parameters.DeviceIoControl.InputBufferLength</b> specifies the size, in bytes, of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff541052">INTERNAL_I8042_START_INFORMATION</a> structure.

### Output Buffer
None

### Output Buffer Length
None

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to STATUS_SUCCESS.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntdd8042.h (include Ntdd8042.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541052">INTERNAL_I8042_START_INFORMATION</a>