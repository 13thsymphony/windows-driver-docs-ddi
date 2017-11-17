---
UID: NI.hidport.IOCTL_HID_ACTIVATE_DEVICE
title: IOCTL_HID_ACTIVATE_DEVICE
author: windows-driver-content
description: The IOCTL_HID_ACTIVATE_DEVICE request activates a HIDClass device, which makes it ready for I/O operations.
old-location: hid\ioctl_hid_activate_device.htm
ms.assetid: 5d2f218c-a9a5-4149-8fde-898171dfc9a7
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: ioctl
ms.prod: windows-hardware
ms.technology: hid
req.header: hidport.h
req.include-header: Hidport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_HID_ACTIVATE_DEVICE
req.alt-loc: hidport.h
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
ms.keywords: HidRegisterMinidriver
req.iface: 
---

# IOCTL_HID_ACTIVATE_DEVICE IOCTL



## -description
<p>The IOCTL_HID_ACTIVATE_DEVICE request activates a HIDClass device, which makes it ready for I/O operations.</p>
<p>For general information about HIDClass devices, see <a href="NULL">HID Collections</a>. </p>


## -ioctlparameters

### -input-buffer
<p><b>Parameters.DeviceIoControl.Type3InputBuffer</b> contains a collection identifier, as a ULONG value, of the collection to activate.</p>

### -input-buffer-length
<p>The length of a ULONG value.</p>

<p>The length of a ULONG value.</p>

### -output-buffer
<p>None.</p>

<p>None.</p>

<p>None.</p>

### -output-buffer-length
<p>None.</p>

<p>None.</p>

<p>None.</p>

<p>None.</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>
       HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to zero.</p>

<p><b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.</p>

<p>Minidrivers that call other drivers with this IRP to carry out the I/O to their device should ensure that the <b>Information</b> field of the status block is zero and not change the contents of the <b>Status</b> field.</p>

<p>
       HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to zero.</p>

<p><b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.</p>

<p>Minidrivers that call other drivers with this IRP to carry out the I/O to their device should ensure that the <b>Information</b> field of the status block is zero and not change the contents of the <b>Status</b> field.</p>

<p>
       HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to zero.</p>

<p><b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.</p>

<p>Minidrivers that call other drivers with this IRP to carry out the I/O to their device should ensure that the <b>Information</b> field of the status block is zero and not change the contents of the <b>Status</b> field.</p>

<p>
       HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to zero.</p>

<p><b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.</p>

<p>Minidrivers that call other drivers with this IRP to carry out the I/O to their device should ensure that the <b>Information</b> field of the status block is zero and not change the contents of the <b>Status</b> field.</p>

<p>
       HID minidrivers that carry out the I/O to the device set the following fields of <b>Irp-&gt;IoStatus</b>:</p>

<p><b>Information</b> is set to zero.</p>

<p><b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.</p>

<p>Minidrivers that call other drivers with this IRP to carry out the I/O to their device should ensure that the <b>Information</b> field of the status block is zero and not change the contents of the <b>Status</b> field.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hidport.h (include Hidport.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541075">IOCTL_HID_DEACTIVATE_DEVICE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_ACTIVATE_DEVICE control code%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
