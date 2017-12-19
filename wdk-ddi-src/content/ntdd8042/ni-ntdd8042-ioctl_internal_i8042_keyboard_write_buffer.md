---
UID: NI.ntdd8042.IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER
title: IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER
author: windows-driver-content
description: The IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a keyboard device.
old-location: hid\ioctl_internal_i8042_keyboard_write_buffer.htm
old-project: hid
ms.assetid: 583263fc-8b95-47d9-9f20-306b2200b573
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _MOUSE_STATE, MOUSE_STATE, PMOUSE_STATE, *PMOUSE_STATE
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
req.alt-api: IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER
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

# IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER IOCTL



## -description

The IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a keyboard device. A filter driver can use this request to control the operation of a keyboard.

I8042prt synchronizes write buffer requests and other keyboard requests that write to the i8042 port controller, including <a href="hid.ioctl_keyboard_set_indicators">IOCTL_KEYBOARD_SET_INDICATORS</a> and <a href="hid.ioctl_keyboard_set_typematic">IOCTL_KEYBOARD_SET_TYPEMATIC</a>. I8042prt synchronizes the actual write of data with the keyboard ISR.



The IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER request writes data to the i8042 port controller to control operation of a keyboard device. A filter driver can use this request to control the operation of a keyboard.

I8042prt synchronizes write buffer requests and other keyboard requests that write to the i8042 port controller, including <a href="hid.ioctl_keyboard_set_indicators">IOCTL_KEYBOARD_SET_INDICATORS</a> and <a href="hid.ioctl_keyboard_set_typematic">IOCTL_KEYBOARD_SET_TYPEMATIC</a>. I8042prt synchronizes the actual write of data with the keyboard ISR.



## -ioctlparameters

### -input-buffer
<b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to a client-allocated buffer which inputs the data to write to an i8042 port controller.


### -input-buffer-length
<b>Parameters.DeviceIoControl.InputBufferLength</b> is set to the number of bytes in the input buffer, which must be greater than one.


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
The <b>Status</b> member is set to one of the following values:



The request completed successfully.

The keyboard interrupt is not initialized.

The input parameters are not valid.

The request timed out.


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
<a href="hid.ioctl_keyboard_set_indicators">IOCTL_KEYBOARD_SET_INDICATORS</a>
</dt>
<dt>
<a href="hid.ioctl_keyboard_set_typematic">IOCTL_KEYBOARD_SET_TYPEMATIC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_INTERNAL_I8042_KEYBOARD_WRITE_BUFFER control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

