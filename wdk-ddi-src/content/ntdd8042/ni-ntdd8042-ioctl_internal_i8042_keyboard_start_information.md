---
UID: NI.ntdd8042.IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
title: IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
author: windows-driver-content
description: The IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION request passes a pointer to a keyboard interrupt object.
old-location: hid\ioctl_internal_i8042_keyboard_start_information.htm
old-project: hid
ms.assetid: a589b1e1-7462-4de7-83df-c3d55fa01b76
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _MOUSE_STATE, MOUSE_STATE, *PMOUSE_STATE
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
req.alt-api: IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION
req.alt-loc: ntdd8042.h
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
---

# IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION IOCTL



## -description

The IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION request passes a pointer to a keyboard interrupt object. I8042prt sends this request synchronously to the top of the device stack after the keyboard interrupt object is created. Upper-level filter drivers that need to synchronize their callback operation with the I8042prt keyboard ISR can use the pointer to the keyboard interrupt object.

The IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION request passes a pointer to a keyboard interrupt object. I8042prt sends this request synchronously to the top of the device stack after the keyboard interrupt object is created. Upper-level filter drivers that need to synchronize their callback operation with the I8042prt keyboard ISR can use the pointer to the keyboard interrupt object.


## -ioctlparameters

### -input-buffer
<b>AssociatedIrp.SystemBuffer</b> points to a buffer allocated by I8042prt to input an <a href="hid.internal_i8042_start_information">INTERNAL_I8042_START_INFORMATION</a> structure.

### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> specifies the size, in bytes, of an <a href="hid.internal_i8042_start_information">INTERNAL_I8042_START_INFORMATION</a> structure.

### -output-buffer
None

### -output-buffer-length
None

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to STATUS_SUCCESS.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntdd8042.h (include Ntdd8042.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="hid.internal_i8042_start_information">INTERNAL_I8042_START_INFORMATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_INTERNAL_I8042_KEYBOARD_START_INFORMATION control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
