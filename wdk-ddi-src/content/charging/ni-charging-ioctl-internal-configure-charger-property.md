---
UID: NI.charging.IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY
title: IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY
author: windows-driver-content
description: The IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY control code is sent from a configurable charger to a device that handles configurable chargers. It configures charger properties.
old-location: battery\ioctl_internal_configure_charger_property.htm
old-project: battery
ms.assetid: B4D10667-29D6-45BF-87CA-D2F59DF78797
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: BTHX_VERSION, BTHX_VERSION, *PBTHX_VERSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: charging.h
req.include-header: Charging.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10 and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY
req.alt-loc: charging.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY IOCTL



## -description
<p>The <b>IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY</b> 
   control code is sent from a configurable charger to a device that handles configurable chargers. It configures charger properties.</p>


## -ioctlparameters

### -input-buffer
<p><b>Irp-&gt;AssociatedIrp.SystemBuffer</b> must contain a structure that starts with a <a href="..\charging\ns-charging--configurable-charger-property-header.md">CONFIGURABLE_CHARGER_PROPERTY_HEADER</a> structure.</p>

### -input-buffer-length
<p><b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.</p>

<p><b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer.</p>

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
<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS or the appropriate error status.</p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS or the appropriate error status.</p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS or the appropriate error status.</p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS or the appropriate error status.</p>

<p><b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS or the appropriate error status.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Windows 10 and later operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Charging.h (include Charging.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\charging\ns-charging--configurable-charger-property-header.md">CONFIGURABLE_CHARGER_PROPERTY_HEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [battery\battery]:%20IOCTL_INTERNAL_CONFIGURE_CHARGER_PROPERTY control code%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
