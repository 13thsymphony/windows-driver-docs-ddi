---
UID: NI.acpiioct.IOCTL_ACPI_RELEASE_GLOBAL_LOCK
title: IOCTL_ACPI_RELEASE_GLOBAL_LOCK
author: windows-driver-content
description: The IOCTL_ACPI_RELEASE_GLOBAL_LOCK device control request is reserved for internal use only.
old-location: acpi\ioctl_acpi_release_global_lock.htm
old-project: acpi
ms.assetid: dcc74af4-500b-4fea-ba2b-9d1ea3a05ef6
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: UNIT_ISOCH_PARAMS, UNIT_ISOCH_PARAMS, *PUNIT_ISOCH_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_ACPI_RELEASE_GLOBAL_LOCK
req.alt-loc: Acpiioct.h
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

# IOCTL_ACPI_RELEASE_GLOBAL_LOCK IOCTL



## -description
<p>The IOCTL_ACPI_RELEASE_GLOBAL_LOCK device control request is reserved for internal use only.</p>


## -ioctlparameters

### -input-buffer

<text></text>

### -input-buffer-length

<text></text>

### -output-buffer

<text></text>

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Windows Vista and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Acpiioct.h (include Acpiioct.h)</dt>
</dl>
</td>
</tr>
</table>