---
UID: NI:lamp.IOCTL_LAMP_SET_EMITTING_LIGHT
title: IOCTL_LAMP_SET_EMITTING_LIGHT
author: windows-driver-content
description: The IOCTL_LAMP_SET_EMITTING_LIGHT control code turns the lamp on or off.
old-location: stream\ioctl_lamp_set_emitting_light.htm
old-project: stream
ms.assetid: E3B85C82-EC55-4A88-BFCA-91123F8311D1
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.ioctl_lamp_set_emitting_light, IOCTL_LAMP_SET_EMITTING_LIGHT control code [Streaming Media Devices], IOCTL_LAMP_SET_EMITTING_LIGHT, lamp/IOCTL_LAMP_SET_EMITTING_LIGHT
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
-	IOCTL_LAMP_SET_EMITTING_LIGHT
product: Windows
targetos: Windows
req.typenames: LAMP_MODE
---

# IOCTL_LAMP_SET_EMITTING_LIGHT IOCTL
The <b>IOCTL_LAMP_SET_EMITTING_LIGHT</b> 
   control code turns the lamp on or off.
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define IOCTL_LAMP_SET_EMITTING_LIGHT \
    CTL_CODE(IOCTL_LAMP_BASE, 0x0009, METHOD_BUFFERED, FILE_ANY_ACCESS)</pre>
</td>
</tr>
</table></span></div>

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<code>Irp-&gt;AssociatedIrp.SystemBuffer</code> points to a buffer of type <b>BOOLEAN</b>, with <b>TRUE</b> indicating a request to turn the lamp on; <b>FALSE</b> otherwise.

### Input Buffer Length
Length of a <b>BOOLEAN</b>.

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

If the device has been acquired by a camera driver, the lamp driver should return a <b>STATUS_RESOURCE_IN_USE</b> error via <code>Irp-&gt;IoStatus.Status</code>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | lamp.h |