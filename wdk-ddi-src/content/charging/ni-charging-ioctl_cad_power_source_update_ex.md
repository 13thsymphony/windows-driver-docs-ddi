---
UID: NI.charging.IOCTL_CAD_POWER_SOURCE_UPDATE_EX
title: IOCTL_CAD_POWER_SOURCE_UPDATE_EX
author: windows-driver-content
description: This IOCTL is for internal use only.
old-location: battery\ioctl_cad_power_source_update_ex.htm
old-project: battery
ms.assetid: 8D582EF9-B9D1-498B-AE20-337F3A33250C
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _POWERSOURCEID, *PPOWERSOURCEID, POWERSOURCEID, PPOWERSOURCEID
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: charging.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_CAD_POWER_SOURCE_UPDATE_EX
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
req.irql: 
---

# IOCTL_CAD_POWER_SOURCE_UPDATE_EX IOCTL



## -description
This IOCTL is for internal use only.



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
Header

</th>
<td width="70%">
<dl>
<dt>Charging.h</dt>
</dl>
</td>
</tr>
</table>