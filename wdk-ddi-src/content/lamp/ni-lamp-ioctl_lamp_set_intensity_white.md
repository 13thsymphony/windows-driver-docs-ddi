---
UID: NI:lamp.IOCTL_LAMP_SET_INTENSITY_WHITE
title: IOCTL_LAMP_SET_INTENSITY_WHITE
author: windows-driver-content
description: The IOCTL_LAMP_SET_INTENSITY_WHITE control code sets the lamp to the specified light intensity.
old-location: stream\ioctl_lamp_set_intensity_white.htm
old-project: stream
ms.assetid: 78541C4C-AA0E-4C1F-A7B5-E2A39DF5E2CE
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ioctl_lamp_set_intensity_white, IOCTL_LAMP_SET_INTENSITY_WHITE control code [Streaming Media Devices], IOCTL_LAMP_SET_INTENSITY_WHITE, lamp/IOCTL_LAMP_SET_INTENSITY_WHITE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: lamp.h
req.include-header: 
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
-	lamp.h
apiname:
-	IOCTL_LAMP_SET_INTENSITY_WHITE
product: Windows
targetos: Windows
req.typenames: LAMP_MODE
---

# IOCTL_LAMP_SET_INTENSITY_WHITE IOCTL
The <b>IOCTL_LAMP_SET_INTENSITY_WHITE</b> 
   control code sets the lamp to the specified light intensity.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define IOCTL_LAMP_SET_INTENSITY_WHITE \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0005, METHOD_BUFFERED, FILE_ANY_ACCESS)</pre>
</td>
</tr>
</table></span></div>

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> points to a <a href="..\lamp\ns-lamp-lamp_intensity_white.md">LAMP_INTENSITY_WHITE</a> structure.

### Input Buffer Length
Length of a <a href="..\lamp\ns-lamp-lamp_intensity_white.md">LAMP_INTENSITY_WHITE</a> structure.

### Output Buffer
None.

### Output Buffer Length
None.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The driver sets <code>Irp-&gt;IoStatus.Status</code> to <b>STATUS_SUCCESS</b> or the appropriate error status.

If the device has been acquired by a camera driver, the lamp driver should return a  <b>STATUS_RESOURCE_IN_USE</b> error via <code>Irp-&gt;IoStatus.Status</code>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | lamp.h |