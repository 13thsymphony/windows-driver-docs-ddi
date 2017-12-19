---
UID: NI.ntdd8042.IOCTL_INTERNAL_I8042_HOOK_KEYBOARD
title: IOCTL_INTERNAL_I8042_HOOK_KEYBOARD
author: windows-driver-content
description: The IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request does the following:Adds an initialization callback routine to the I8042prt keyboard initialization routineAdds an ISR callback routine to the I8042prt keyboard ISRThe initialization and ISR callbacks are optional and are provided by an upper-level filter driver for a PS/2-style keyboard device.After I8042prt receives an IOCTL_INTERNAL_KEYBOARD_CONNECT request, it sends a synchronous IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request to the top of the keyboard device stack.After Kbfiltr receives the hook keyboard request, Kbfiltr filters the request in the following way:Saves the upper-level information passed to Kbfiltr, which includes the context of an upper-level device object, a pointer to an initialization callback, and a pointer to an ISR callbackReplaces the upper-level information with its ownSaves the context of I8042prt and pointers to callbacks that the Kbfiltr ISR callback can useFor more information about this request and the callbacks, see the following topics:I8042prt Callback RoutinesKbfiltr Callback Routines.
old-location: hid\ioctl_internal_i8042_hook_keyboard.htm
old-project: hid
ms.assetid: 74580730-1cbb-40fb-a4a3-20523f933171
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
req.alt-api: IOCTL_INTERNAL_I8042_HOOK_KEYBOARD
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

# IOCTL_INTERNAL_I8042_HOOK_KEYBOARD IOCTL



## -description

The IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request does the following:

<ul>
<li>
Adds an initialization callback routine to the I8042prt keyboard initialization routine

</li>
<li>
Adds an ISR callback routine to the I8042prt keyboard ISR

</li>
</ul>
The initialization and ISR callbacks are optional and are provided by an upper-level filter driver for a PS/2-style keyboard device.

After I8042prt receives an <a href="..\kbdmou\ni-kbdmou-ioctl_internal_keyboard_connect.md">IOCTL_INTERNAL_KEYBOARD_CONNECT</a> request, it sends a synchronous IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request to the top of the keyboard device stack.

After Kbfiltr receives the hook keyboard request, Kbfiltr filters the request in the following way:

<ul>
<li>
Saves the upper-level information passed to Kbfiltr, which includes the context of an upper-level device object, a pointer to an initialization callback, and a pointer to an ISR callback

</li>
<li>
Replaces the upper-level information with its own

</li>
<li>
Saves the context of I8042prt and pointers to callbacks that the Kbfiltr ISR callback can use

</li>
</ul>
For more information about this request and the callbacks, see the following topics:

<dl>
<dd>

<a href="hid.i8042prt_callback_routines">I8042prt Callback Routines</a>


</dd>
<dd>

<a href="https://msdn.microsoft.com/a939a2f1-740d-4d6e-a908-cfbefc0808a2">Kbfiltr Callback Routines</a>


</dd>
</dl>


The IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request does the following:

Adds an initialization callback routine to the I8042prt keyboard initialization routine

Adds an ISR callback routine to the I8042prt keyboard ISR

The initialization and ISR callbacks are optional and are provided by an upper-level filter driver for a PS/2-style keyboard device.

After I8042prt receives an <a href="..\kbdmou\ni-kbdmou-ioctl_internal_keyboard_connect.md">IOCTL_INTERNAL_KEYBOARD_CONNECT</a> request, it sends a synchronous IOCTL_INTERNAL_I8042_HOOK_KEYBOARD request to the top of the keyboard device stack.

After Kbfiltr receives the hook keyboard request, Kbfiltr filters the request in the following way:

Saves the upper-level information passed to Kbfiltr, which includes the context of an upper-level device object, a pointer to an initialization callback, and a pointer to an ISR callback

Replaces the upper-level information with its own

Saves the context of I8042prt and pointers to callbacks that the Kbfiltr ISR callback can use

For more information about this request and the callbacks, see the following topics:


<a href="hid.i8042prt_callback_routines">I8042prt Callback Routines</a>



<a href="https://msdn.microsoft.com/a939a2f1-740d-4d6e-a908-cfbefc0808a2">Kbfiltr Callback Routines</a>




## -ioctlparameters

### -input-buffer
The <b>Parameters.DeviceIoControl.Type3InputBuffer</b> points to an INTERNAL_I8042_HOOK_KEYBOARD structure. This structure includes the following members:



Pointer to an optional callback that the I8042prt keyboard initialization routine calls when it initializes a keyboard device.

Pointer to an optional callback that is called by the I8042prt keyboard ISR.


### -input-buffer-length
The <b>Parameters.DeviceIoControl.InputBufferLength</b> member is set to a value that is greater than or equal to the size, in bytes, of an <a href="hid.internal_i8042_hook_keyboard">INTERNAL_I8042_HOOK_KEYBOARD</a> structure.


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

<b>Parameters.DeviceIoControl.InputBufferLength</b> is less than the size, in bytes, of an INTERNAL_I8042_HOOK_KEYBOARD structure.


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
<a href="hid.internal_i8042_hook_keyboard">INTERNAL_I8042_HOOK_KEYBOARD</a>
</dt>
<dt>
<a href="..\kbdmou\ni-kbdmou-ioctl_internal_keyboard_connect.md">IOCTL_INTERNAL_KEYBOARD_CONNECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_INTERNAL_I8042_HOOK_KEYBOARD control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

